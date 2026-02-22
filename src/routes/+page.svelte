<!--
@component
This is your page!
-->
<script>
  // Import all the news furniture components
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import Image from '$lib/components/Image.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';
  import WhyCare from '$lib/components/WhyCare.svelte';
  import AuthorBio from '$lib/components/AuthorBio.svelte';
  import EmbedPDF from '$lib/components/EmbedPDF.svelte';

  // Article metadata
  let headline = 'How $25 and 24 hours can make a wedding official';
  let subheadline = 'One-day officiants now perform one-third of New York City weddings.';
  let byline = 'Jack Walker';
  let pubDate = '2025-12-17';

  // Related stories s
  const relatedStories = [
    { headline: 'Christmas tree disposal requests spiked last holiday', href: 'https://jack-walk.github.io/IRW-01/' },
    { headline: 'HIV prevention cuts would hit lower-resource areas of New York hardest, experts warn', href: 'https://jack-walk.github.io/Data-Assignment-3/' },
    { headline: 'Safety concerns spur $5.1M overhaul for South Jamaica playground', href:"https://www.nycitynewsservice.com/2025/10/14/safety-concerns-spur-5-1m-overhaul-for-south-jamaica-playground/"},
  ];
</script>

<!-- This sets the page title in the browser tab -->
<svelte:head>
  <title>{headline} | NYCity News Service</title>
  <meta name="description" content="At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined." />
</svelte:head>

<!-- Your page content goes here -->
<div class="container">
  
  <!-- Article Header: Headline, byline, and publication date -->
  <ArticleHeader
    {headline}
    {subheadline}
    {byline}
    {pubDate}
  />

  <!-- Lead Image: Animated gif of students at the journalism school -->
  <Image
    src="officiant.jpg"
    alt="A woman in a green dress holds a clipboard and smiles as a woman wearing a white bridal dress approaches."
    caption="Caitlyn Johnson performs a college friend’s wedding as a one-day officiant in Westchester, NY."
    credit="Photo courtesy of Caitlyn Johnson"
  />

  <!-- Why care? A quick summary of the article's significance to readers -->
  <WhyCare
    r1="A growing number of New York City weddings are performed by one-day officiants."
    r2="One-day officiant licensing was approved to create a pathway for officiants without a religious or government affiliation."
    r3="The rise in one-day officiants suggests more New Yorkers are looking for secular or personalized wedding ceremonies."
  />

  <!-- Article Body: The main story text with proper typography -->
  <ArticleBody>
    <p>
      Caitlyn Johnson was a natural choice for the ceremony. In college, she and the bride found unlikely camaraderie over a shared crush. Since then, Johnson stood by through good dates, bad dates and the unexpected Bumble match that led her friend down the aisle.
    </p>

    <p>
      But on the wedding day, Johnson wasn't altarside as a bridesmaid. In a lush Westchester backyard, she stood beneath the arch and braced for a less orthodox role: the wedding officiant. Weeks earlier, she had applied for a single-use license to perform the ceremony.
    </p>

    <p>
      "If that process didn't exist, I don't think she would have asked me," said Johnson, a Long Island City resident who works in tech sales. "To be part of someone's wedding is really special."
    </p>

    <p>About one-third of the city's weddings are now performed by one-day officiants like Johnson, according to City Clerk Michael McSweeney. That's because of a simplified licensing process the state launched in 2023.
    </p>

    <p>
      "It's very popular. It's a very successful program," McSweeney said. "It's a lot easier for an average person to become a marriage officiant legally."
    </p>

    <hr><br>

      <!-- Data viz 1: Percent of all officiants pie chart-->
        <iframe title="Marriage Officiant Registration, April 2023 to October 2025" aria-label="Donut Chart" id="datawrapper-chart-skCRJ" src="https://datawrapper.dwcdn.net/skCRJ/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="613" data-external="1"></iframe><script type="text/javascript">window.addEventListener("message",function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r,i=0;r=e[i];i++)if(r.contentWindow===a.source){var d=a.data["datawrapper-height"][t]+"px";r.style.height=d}}});</script>

    <hr><br>

    <p>
      Gov. Kathy Hochul <a href="https://www.governor.ny.gov/news/governor-hochul-signs-legislation-allowing-individuals-become-one-day-marriage-officiants">signed a law</a> in 2022 allowing residents to perform a single marriage without the lengthy <a href="https://www.cityclerk.nyc.gov/content/marriage-officiant-registration">certification process</a> for religious clergy and government officials. The law took effect in April 2023, letting adults who pay the $25 application fee perform a wedding.
    </p>

    <p>
      A formal one-day process was years in the making. The non-denominational <a href="https://www.ulc.org/about">Universal Life Church</a> ordained residents online for years, and New York City began accepting internet ordination in 2006. The 2022 law simply closed a loophole where some New York counties accepted online ordination and <a href="https://www.tax.ny.gov/pubs_and_bulls/orpts/legal_opinions/v11/90.htm">others did not</a>.
    </p>

    <p>
      Changes like these challenged an implicit view that officiants should be religious, according to Dusty Hoesly, associate director of religious studies at the University of California, Santa Barbara. While religious clergy once performed most weddings, Hoesly said secular ceremonies found favor during a <a href="https://www.pewresearch.org/religion/2019/10/17/in-u-s-decline-of-christianity-continues-at-rapid-pace/">national downturn</a> in religious participation.
    </p>

    <p>
      "How are they getting married? Well, they're probably not going to the Catholic Church of their childhood," Hoesly said. A friend or family member "is going to say things that are based on the deep relationship and authentic connection that they have."
    </p>
    
    <p>
      New York wedding planners widely regard officiant selection as part of the wedding personalization process. The state's new pathway has demystified officiant licensing, helping a wave of newcomers take on the role.
    </p>

    <p>
      "Sometimes it would be quite difficult, trying to get them ordained and correctly recorded as an officiant," said Tzo Ai Ang, founder of Ang Weddings and Events. "It's been quite difficult to get an appointment in time."
    </p>

      <!-- Supplemetal photo: application printouts-->
        <Image
          src="applications.jpg"
          alt="One-day officiant licenses application printouts cover an orange table."
          caption="One-day officiants performed more than 30% of the city’s weddings since April 2023, per the city clerk’s office."
          credit="Photo by Jack Walker/NYCity News Service"
          centered
        />

    <p>
      As a workaround, some couples previously held weddings with an officiant of their choice, then an official ceremony at the courthouse, said Manhattan-based wedding planner Sara Landon. Now, residents can legally and ceremonially wed at the same time.
    </p>

    <p>
      "That ceremonial piece is becoming intertwined," Landon said. "It is a little bit more fun that their friends are signing the marriage licenses."
    </p>

    <p>
      Astoria resident Neil Kernis is used to lecturing as a community college professor, but still found the prospect of officiating his friend's wedding daunting. The one-day officiant process offered him a chance to step outside his comfort zone.
    </p>

    <p>
      "It was a wonderful experience," Kernis said. "I felt like I was part of the wedding in a way that I wouldn't have been if I were just a sort of groomsman, or someone who just attended. I really felt like I was part of a very special day for two people I love."
    </p>

    <p>
      Aspiring one-day officiants can apply through the mail, or an in-person appointment at the City Clerk's Manhattan office. Applications are then processed by the office's Marriage Bureau.
    </p>

    <hr><br>

      <!-- Data viz 2: Rise in number of one-day officiants-->
        <iframe title="More New Yorkers Are Obtaining One-Day Licenses" aria-label="Bar Chart" id="datawrapper-chart-m8bmf" src="https://datawrapper.dwcdn.net/m8bmf/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="169" data-external="1"></iframe><script type="text/javascript">window.addEventListener("message",function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r,i=0;r=e[i];i++)if(r.contentWindow===a.source){var d=a.data["datawrapper-height"][t]+"px";r.style.height=d}}});</script>
    <hr><br>

    <p>
      Thousands of New Yorkers apply to perform weddings each year, McSweeney said. The marriage bureau has successfully incorporated one-day licensing into its existing workflow, even amid a growing number of applications, he said.
    </p>

    <p>
      The number of residents granted one-day marriage officiants more than tripled between April 2023 and October 2025, according to McSweeney. The city's marriage bureau awarded 275 licenses in October, the most recent month of data available.
    </p>

    <p>
      "It's one of the many things that we have to juggle as a small agency," McSweeney said.
    </p>

    <p>
      For one-day officiants, the new process has spurred lifelong memories. When Johnson performed her friend's wedding in May 2024, the couple decided not to recite their vows aloud. That made her role in the ceremony feel all the more important.
    </p>

    <p>
      "I actually had the opportunity to basically speak their vows to each other on behalf of them," she said. "I didn't go on to become an officiant after the fact. But it was certainly a nice memory."
    </p>

  <EmbedPDF
    pdfLink="/one-day-pdf.pdf"
    pdfTitle="DOWNLOAD HERE: One-Day Officiant License Application"
    pdfDateObtained="December 17, 2025"
    pdfSource="New York City Clerk's Office"
    pdfAltDescription="A table showing the number of one-day officiant licenses issued in New York City from April 2023 to October 2025. The table shows a steady increase in licenses issued, with a total of 275 licenses issued in October 2025."
    />

  </ArticleBody>

  <!-- Author Bio: Brief description of who wrote this article -->
  <AuthorBio
    authorPhoto="/jack.jpeg"
    authorName="Jack Walker"
    authorDesc="Jack Walker is a journalist based in New York City and graduate student at the Craig Newmark School of Journalism. Before moving to New York, Jack worked as a journalist in West Virginia for two years and helped run Brown University's student newspaper."
    authorTwitter="https://x.com/jacktmwalker"
    authorEmail="jackwalkerwvgmail.com"
    authorLinkedIn="https://www.linkedin.com/in/jacktmwalker/"
    authorLink="https://jackwalker.xyz"
  />

  <!-- Related Stories: Links to other articles -->
  <RelatedLinks
    title="Past Reporting"
    links={relatedStories}
  />

</div>

<style>
  /* Styles here only apply to this page */
  .container {
    padding: var(--spacing-lg) var(--spacing-md);
  }
</style>