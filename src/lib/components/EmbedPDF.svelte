<!--
@component
EmbedPDF.svelte — An embedded PDF viewer.

A tool that allows you to view a PDF embedded within an article.

USAGE EXAMPLE:
  <EmbedPDF
    pdfLink="/path/to/document.pdf"
    pdfTitle="Document Title"
    pdfDateObtained="January 1, 2024"
    pdfSource="Source Name"
    pdfAltDescription="A brief description of the PDF content for accessibility.""
  />
-->

<script>
  let { pdfLink, pdfTitle, pdfDateObtained, pdfSource, pdfAltDescription } = $props();
  let isExpanded = $state(false);

  function togglePDF() {
    isExpanded = !isExpanded;
  }
</script>

<div class="pdf-container">
  <div class="pdf-title-box">
    <div class="title-header">
      <p class="pdf-title"><strong>{pdfTitle}</strong></p>
      <button class="toggle-btn" onclick={togglePDF} aria-expanded={isExpanded}>
        {isExpanded ? '▼ Hide' : '▶ View'}
      </button>
    </div>
  </div>
  {#if isExpanded}
    <iframe
      src={pdfLink}
      title={pdfTitle}
      aria-label={pdfAltDescription}
      class="pdf-iframe"
    ></iframe>
  {/if}
</div>

<style>
    .pdf-container {
        margin: 2rem 0;
    }

    .pdf-title-box {
        background-color: var(--color-light-gray);
        padding: 1rem;
        margin-bottom: 0;
        border-radius: 4px 4px 0 0;
    }

    .title-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .pdf-title {
        font-weight: bold;
        margin: 0;
        text-align: center;
        flex: 1;
    }

    .toggle-btn {
        background-color: var(--color-accent);
        color: white;
        border: none;
        padding: 0.5rem 1rem;
        border-radius: 4px;
        cursor: pointer;
        font-size: 0.875rem;
        font-weight: 600;
        transition: background-color 0.2s ease;
        white-space: nowrap;
        margin-left: 1rem;
    }

    .toggle-btn:hover {
        background-color: var(--color-dark);
    }

    .pdf-iframe {
        width: 100%;
        height: 600px;
        border: 1px solid #ccc;
        border-radius: 4px;
    }
</style>