
# Bloomreach Discovery Data Validator - User Guide

## Introduction

The Bloomreach Feed Validator is a Java program designed to verify the correctness of a JSONLines feed file. This guide will walk you through the steps to run the program successfully.

### Prerequisites

Before you begin, make sure you have the following:

- Java Runtime Environment (JRE) installed on your computer.
- The jsonLineAnalyzer-all-1.0-SNAPSHOT.jar file, which you can download from above.

### Installation

- Download the jsonLineAnalyzer-all-1.0-SNAPSHOT.jar file to your computer.
- Choose a suitable directory to save the JAR file; let's call it <PATH>.

### Running the Bloomreach Data Validator
To execute the Bloomreach Data Validator, follow these steps:

- Open your command-line terminal (e.g., Command Prompt on Windows, Terminal on macOS/Linux).
- Navigate to the directory where you saved the JAR file using the cd command. Replace <PATH> with the actual path where you saved the JAR file.

```
cd <PATH>
```
- Run the Bloomreach Feed Validator by executing the following command:
```
java -jar jsonLineAnalyzer-all-1.0-SNAPSHOT.jar jsonLineAnalyzer
```

## Using the Bloomreach Feed Validator UI
The Bloomreach Feed Validator provides a simple user interface (UI) to validate your JSONLines feed file. Follow these steps to use the UI:

- Launch the Bloomreach Feed Validator using the command provided in the previous section.
- In the UI, you will see the following options:

| Parameter | Description                       |
| :-------- | :-------------------------------- |
| File Name      |  **Required**. Enter the name or choose your JSONLines feed file. |
| Type of File    |  **Required**. Specify the type of file (e.g., JSONLines). |
| No. of JSONLines to Scan   |  **Required**. Enter the number of lines you want to scan.. |
| Pause at Each Line   |  **Required**. Select "Yes" if you want to pause and review each line during validation. Otherwise, select "No" to skip pausing. |

- Once you've filled in all the required fields, click on the "Validate DC Feed" button to start the validation process.
- If you chose "Yes" for pausing at each line, you will need to click on the "Continue" button to review each line individually. You can also click on "Nomore Pausing" to skip pausing for the remaining lines.

![SNAPSHOT](https://github.com/bloomreach/bloomreach-discovery-data-validator/blob/data-validator-v1/screenshots/ss1.png)

![SNAPSHOT](https://github.com/bloomreach/bloomreach-discovery-data-validator/blob/data-validator-v1/screenshots/ss2.png)


## Viewing Validation Results

After clicking "Validate DC Feed," you will see the validation details for each JSON line. These details include information about each line's validation status.

When the validation is complete, you will find the following output files:

`XYZ.jsonl`: The original input file.

`XYZ.jsonl-analysis`: A detailed analysis of each line.

`XYZ.jsonl-attrs.tsv`: A list of all attributes in the input file.

`XYZ.jsonl-bad_lines.tsv`: A file containing lines that are flagged as invalid, possibly due to missing mandatory fields or formatting issues.

`XYZ.jsonl-duplicatePids.tsv`: A list of duplicate product IDs (lines).

## Mandatory Fields

The Bloomreach Feed Validator checks for the presence of the following mandatory fields in each JSON line:
- `title`
- `url`
- `price`

Note that the absence of price at the product level can be ignored if it is present at the variant level or view level.
