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
        <p>In every legislative session between 2016 and 2022, a bill titled <em>Protect Human Life At Conception</em> has been proposed. Each time it was introduced, the result was the same: postponed indefinitely in its first committee hearing. So, why was it repeatedly introduced? What motivates lawmakers to continue pushing bills that have been doomed from the beginning?</p>
        <p>Legislatures are built to tackle issues, and abortion is one at the forefront of Colorado citizens’ minds. However, when legislators repeatedly introduce nearly identical bills, it raises questions about legislative priorities and motivations. Does this persistence signify a genuine commitment to a cause, a strategy to influence public opinion, or simply a symbolic gesture meant to keep conversation going? Do voting outcomes change with each repeated proposal, or are the results as static as the texts themselves? Understanding the dynamics that influence voting on this bill can help illuminate the strategy behind ‘Message Bills’ as a whole.</p>
        <p>To investigate this phenomenon, I gathered data on the <em>Protect Human Life at Conception</em> bill series from publicly available legislative records on the Colorado Legislature website. These bills were introduced annually from 2016 to 2022, each time following a near-identical trajectory: postponed indefinitely after a committee hearing. The table below summarizes key details of each bill, including the year it was proposed, the prime sponsors, and the voting outcomes:</p>
        <div class="center-frame">
            <iframe src="./Graph/PHLC_table1.html" height="500" width="800" frameborder="0"></iframe>
        </div>
        <p>While additional prime sponsors on these bills change throughout the years, one representative, Stephen Humphrey, championed the bill in every session between 2016 and 2020, before handing the responsibility to Rep. Patrick Neville, who was the sole prime sponsor of the bill until its final proposal in January of 2022. Were these changes in prime sponsorship reflected in the textual content of the bills? To answer this question, I conducted a textual analysis of each bill text and compared it to the original 2016 bill text.</p>
    </div>
</body>
</html>
