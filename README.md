<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* General Body Styles */
        body {
            margin: 0; /* Remove default margins */
            font-family: Arial, sans-serif; /* Use clean font */
            line-height: 1.6;
            background-color: #f9f9f9; /* Light background */
        }
        /* Container to Center Content */
        .content-container {
            max-width: 800px; /* Restrict width */
            margin: 40px auto; /* Center content */
            padding: 20px;
            background-color: #ffffff; /* White background for contrast */
            border: 1px solid #ddd; /* Light border for a polished look */
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Add slight shadow */
            border-radius: 8px; /* Rounded corners */
        }
        /* Header Styles */
        .header h1 {
            text-align: center; /* Center the header text */
            margin-bottom: 20px;
            font-size: 28px;
            color: #333;
        }
        /* Paragraph Styles */
        p {
            text-align: justify; /* Justify text for neatness */
            margin-bottom: 16px;
        }
        /* Table / iframe Centering */
        .center-frame {
            display: flex;
            justify-content: center;
            margin: 20px 0;
        }
    </style>
</head>

<body>
    <div class="content-container">
        <div class="header">
            <h1>Colorado Legislators Propose Doomed Bill, 6 Years Straight</h1>
        </div>
        <h2>Introduction</h2>
        <p>In every legislative session between 2016 and 2022, a bill titled <em>Protect Human Life At Conception</em> has been proposed. Each time it was introduced, the result was the same: postponed indefinitely in its first committee hearing. So, why was it repeatedly introduced? What motivates lawmakers to continue pushing bills that have been doomed from the beginning?</p>
        <p>Legislatures are built to tackle issues, and Abortion is one at the forefront of Colorado citizens’ minds. Constituents across the state want to see their positions represented, but when legislators repeatedly introduce nearly identical bills, it raises questions about legislative priorities and motivations. Each proposed bill involves hours or even days of committee hearings, fiscal report creation, etc. Does this persistence signify a genuine commitment to a cause, a strategy to influence public opinion, or simply a symbolic gesture meant to keep conversation going? Do voting outcomes change with each repeated proposal, or are the results as static as the texts themselves? Understanding the dynamics that influence voting on this bill can help illuminate the strategy behind ‘Message Bills’ as a whole. 
</p>
        <p>To investigate this phenomenon, I gathered data on the <em>Protect Human Life at Conception</em> bill series from publicly available legislative records on the Colorado Legislature website. These bills were introduced annually from 2016 to 2022, each time following a near-identical trajectory: postponed indefinitely after a committee hearing. The table below summarizes key details of each bill, including the year it was proposed, the prime sponsors, and the voting outcomes:</p>
        <div class="center-frame">
            <iframe src="./Graph/PHLC_table1.html" height="500" width="800" frameborder="0"></iframe>
        </div>
        <p>While additional prime sponsors on these bills change throughout the years, one representative, Stephen Humphrey, championed the bill in every session between 2016 and 2020, before handing the responsibility to Rep. Patrick Neville, who was the sole prime sponsor of the bill until its final proposal in January of 2022. Were these changes in prime sponsorship reflected in the textual content of the bills? To answer this question, I conducted a textual analysis of each bill text and compared it to the original 2016 bill text.</p>
        <h2>Textual Analysis</h2>
        <p>To get the full text for each iteration of the bill, I utilized python libraries <a href="https://pypi.org/project/requests/" target="_blank">Requests</a>, <a href="https://pypi.org/project/beautifulsoup4/" target="_blank">BeautifulSoup</a>, and <a href="https://pypi.org/project/pypdf/" target="_blank">PyPDF</a> to access, extract, and clean text each of the corresponding bill pages on the   <a href="https://leg.colorado.gov/" target="_blank">Colorado Legislature</a> website.

In order to compare the content of each subsequent bill, each bill’s text was converted to embeddings using the <a href="https://platform.openai.com" target="_blank">OpenAI API</a>. Converting text to embeddings involves converting the text document into numerical representations, or vectors. Similar words, sentences, or phrases will have vectors that are closer together, while unrelated words will have vectors that are further apart. Once the bill texts were converted to vectors, cosine similarity was used to measure how similar the vectors of each bill were to the first bill. Cosine similarity calculates the angle between two vectors, where a smaller angle means the texts are more similar. The result is a score between 0 and 1: a score closer to 1 means the texts are nearly identical, while a score closer to 0 means they are very different. </p>
        <div class="center-frame">
            <img src="./img/cosine_similarity_heatmap.png" height="400" width="400">
        </div>
    <p>This figure shows that each bill’s text is nearly identical, with the smallest of differences occurring in 2021, but this change is not nearly significant enough to point towards an amendment or real change in the content or overall tone of the bill. This change occurred when Rep. Patrick Neville became the sole prime sponsor of the bill. However, this change is so miniscule that it is likely a result of changing the prime sponsor name at the beginning of the bill text. The lack of textual edits suggests that lawmakers were not revising the bill to address previous criticisms or adapting it whatsoever. While change in prime sponsor did not result in a change in bill text, a few interesting trends emerge when analyzing the bills co-sponsors and supporters. </p>
    <h2>Changes in Sponsorship and Voting Outcomes</h2>
    <p>Sponsors are the legislators that co-sign the bill after it is introduced. Sponsor counts can help us get a better understanding of how popular a bill is within its respective legislative body, in this case, it's the house. To analyze sponsorship patterns, I used the same python libraries (Requests and BeautifulSoup) to find and count the number of sponsors, and plotly express to create an interactive line graph showing the sponsor counts over time. </p>
        <div class="center-frame">
            <iframe src="./Graph/sponsors.html" height="500" width="800" frameborder="0"></iframe>
        </div>
    <p>The dwindling number of sponsors for this bill over its lifetime is glaring. Although initial support for the bill was high, with over 20 sponsors in the first four years it was proposed, by 2022, sponsorship dwindled in numbers, ending with only 4 lawmakers sponsoring the bill. These sharp changes in sponsorship could be a result of a few things:</p>

<p>Prime Sponsorship Changes: Hovering over the graph above reveals the prime sponsors for each year, you’ll notice that throughout the years, both the senate and the house were represented in the prime sponsors. Coupled with already high support within the republican party, having representation across both House and Senate would encourage more co-sponsors. However, In 2021 and 2022, Rep. Patrick Neville was the sole prime for an aging bill, which likely contributed to its lack of support. </p>

<p><a href="https://reproductiverights.org/maps/state/colorado/" target="_blank">A Failed Ballot Initiative</a>: In November of 2020, voters rejected a ballot initiative that would have banned abortion after 20 weeks. This result may have contributed to dwindling support in 2020. </p>

<p>This dwindling support can also be seen in the committee voting results. Each year that Protect Human Life At Conception was introduced, it was sent to the Health & Insurance Committee (prev. Health, Insurance & Environment Committee). The first action this committee has taken regarding this bill has been to postpone it indefinitely, the chart below shows the voting results for this action over the bill’s lifespan:  </p>
        <div class="center-frame">
            <iframe src="./Graph/voting_stacked.html" height="500" width="800" frameborder="0"></iframe>
        </div>
<p>Similar to the trends in sponsorship, this bill was at its strongest between 2016 and 2018. In each of those years, the bill was just one vote away from passing to the next step in the legislative process, but that small victory was just that, small. As time passed, just as sponsorship dwindled, so did the already minimal support within the committee, with the margin of victory for indefinite postponement grew to 3 votes. In fact, further digging shows that in 2016, 2017, and 2018, Representative Stephen Humphrey, a prime sponsor of the bill at that time, was also a member of the Health, Insurance & Environment Committee. This dual role was likely responsible for the closer margins, as Rep. Humphrey was able to directly advocate for the bill during discussions and hearings. In 2019, Rep. Humphrey was removed from the committee, and voting margins increased. 

Overall, there is a place for these ‘Message Bills’ in the legislature. Although an increasingly democratic house of representatives does not paint a positive picture for this particular one, former Republican Rep. Justin Everett said this to <a href="https://www.cpr.org/2017/03/09/why-colorado-lawmakers-propose-bills-they-know-wont-pass/" target="_blank">Colorado Public Radio</a>: "You can't really let that issue die just because the lines in the legislature are drawn to favor one party, especially in the House, we still need to have these conversations and show people that yeah, I mean, this is still an issue that matters. It's not just something that falls by the wayside. Until something changes in the right direction, I think we'll keep on having these dialogues."</p>
<h2>Limitations and Future Directions</h2>
<p>
This analysis is limited by its scope, focusing exclusively on one bill with a single title, inside of a single legislative body.  In order to truly understand the patterns associated with repeated bill proposals, or ‘Message Bills’, it is essential to expand our analysis in a few different directions. 
Firstly, collecting other examples of these bills that fall under additional subjects and legislative priorities could show if the trends identified in this case study are universal. Specifically, finding other repeated bills across parties and legislative bodies (the Senate) would be an interesting way to contrast this strictly-republican bill. Secondly, looking at public approval ratings in the districts of those sponsoring these bills, as well as their campaign messaging, could provide more insight into the reasoning behind these repeated bills. The reasoning behind these repeated bills is said to be to please constituents, so understanding if making these conversations happen in legislative bodies is sufficient enough for constituents, even if the bill isn’t passed, would be very interesting. 
</p>
    </div>
</body>
</html>
