<!--
@component
AuthorBio.svelte — An infobox with information on the article's author.

An infobox featuring a photo, name and description of the article's author.
Also includes links to author's social media accounts.

USAGE EXAMPLE:
  <AuthorBio
    authorPhoto="/jack.jpeg"
    authorName="Jack Walker"
    authorDesc="Jack Walker is a journalist based in New York City and graduate student at the Craig Newmark School of Journalism. Before moving to New York, Jack worked as a journalist in West Virginia for two years and helped run Brown University's student newspaper."
    authorTwitter="https://x.com/jacktmwalker"
    authorEmail="jackwalkerwvgmail.com"
    authorLinkedIn="https://www.linkedin.com/in/jacktmwalker/"
    authorLink="https://jackwalker.xyz"
  />
-->

<script>
  let { authorPhoto, authorName, authorDesc, authorTwitter, authorEmail, authorLinkedIn, authorLink } = $props();
</script>

<div class="authorContainer">


    <!-- Infobox Navigation -->
    <nav class="infobox-nav" aria-label="Infobox navigation">
    <div class="side1">
        <img class="authorImg" src={authorPhoto} alt="A portrait photo of {authorName}."/>
        <br><p>Author: <b><a href={authorLink}>{authorName}</a></b></p></div>
        <span class="infobox-divider"></span>
        <div class="side2">
        <p class="authorDesc">{authorDesc}</p>
        
        <div class="social-links">
        {#if authorTwitter}
            <a href={authorTwitter} class="Twitter"><img class = "twitterImg"src="/twitter.png" alt="Twitter icon"></a>
        {/if}

        {#if authorEmail}
            <a href={"mailto:" + authorEmail} class="Email"><img class="emailImg"src="/email.png" alt="Email icon"></a>
        {/if}

        {#if authorLinkedIn}
            <a href={authorLinkedIn} class="LinkedIn"><img class="linkedInImg"src="/linkedin.png" alt="LinkedIn icon"></a>
        {/if}
        </div></div>
    </nav>
</div>

<style>
  .authorContainer {
    margin: 2rem 0;
    padding: 1rem;
    padding-left: 5rem;
    padding-right: 3rem;
    border: 6px solid var(--color-accent);
    background-color: var(--color-light-gray);
  }

  .infobox-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
  }

  .side1 {
    flex: 0 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 5px 10px 10px 5px;
  }

  .side2 {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 10px;
  }

    .infobox-divider {
        width: 2px;
        background-color: var(--color-medium-gray);
        margin: 0 1rem;
        align-self: stretch;
    }

.authorImg{
    border-radius: 25px;
    margin: 0 auto;
    width: 200px;
    height: 200px;
}

.authorName{
    font-size: 1.25rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
    margin-top: 0.75rem;
    color: var(--color-dark);
    text-align: center;
}

.authorDesc {
    font-family: 'Courier New', monospace;
    font-size: 0.95rem;
    line-height: 1.5;
}

.social-links {
    display: flex;
    gap: 0.75rem;
    margin-top: 0.5rem;
    justify-content: center;
    width: 100%;
}

.Twitter {
    margin-right: 0.5rem;
}

.twitterImg {
    width: 20px;
    height: 20px;
    align: center;
}

.LinkedIn {
    margin-right: 0.5rem;
}

.linkedInImg {
    width: 20px;
    height: 20px;
    align: center;
}

.Email {
    margin-right: 0.5rem;
}

.emailImg {
    width: 20px;
    height: 20px;
    align: center;
}
</style>