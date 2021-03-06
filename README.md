# LegalDocNLP
Legal Document Summarizer Project for QMIND

# Jan 25, 2022
There exist two types of ways to create a text summary from an AI, which is expolained below by Jason Brownlee from machinelearningmastery.com:

"There are two main approaches to summarizing text documents; they are:

1. Extractive Methods.
2. Abstractive Methods.

"The different dimensions of text summarization can be generally categorized based on its input type (single or multi document), purpose (generic, domain specific, or query-based) and output type (extractive or abstractive)."

— A Review on Automatic Text Summarization Approaches, 2016.

Extractive text summarization involves the selection of phrases and sentences from the source document to make up the new summary. Techniques involve ranking the relevance of phrases in order to choose only those most relevant to the meaning of the source.

Abstractive text summarization involves generating entirely new phrases and sentences to capture the meaning of the source document. This is a more challenging approach, but is also the approach ultimately used by humans. Classical methods operate by selecting and compressing content from the source document."

We will likely be focusing on extractive simply because it'll be a less tedious and tough pill to swallow. As such, we'll need to gather up the HTML files from Canada Gazette and treat them accordingly. 

A really great starting point for this material is done on Github by user LaurentVeyssier. See his project here:

We'll be doing our first attempts for this project using his methodology and attempting a solution with TextRank. Should that not work, another common algorithm is seq2seq but this is a bit more technical and requires knowledge of RNN's so we'll save it as a backup for now.

To prepare for the implementation for our next meeting, please move about 10 Canada Gazette sections into a text file and dump them into the created folder "Gazette Extractions". Gazette sections aren't the whole thing, so no need to freak out. They're just the smaller pieces of into separated by headings. See the folder for some examples that I moved in for now. From there, we'll discuss next steps.

# Feb 2, 2022
We'll be converting the text files in the extractions folde rinto a readable CSV. CSV's are the base format for most, if not all, ML datasets. We'll be creating our CSV from Google Sheets, which is n the running meeting notes google doc. From here, we'll bigin the actual coding scrums, and have created either a Python Jupyter Notebook or raw Python file. Things are moving along!

# Feb 19, 2022
We'll be moving along with the following demo. To really sum up what's happening in this demo, they basically use TextRank and its predecessor, PageRank, to sort through tennis articles. They create a data point for each sentence, and analyze various data points. Take a look through this guide, as we'll be replicating a similar thing. The main change we'll be making is because Canada Gazette posts vary in length, we want to make the number of sentences for the summary dynamic rather than the 5 they use, so the main task over reading week will be to explore how we can potentially create a dynamic anlysis of sentences rather than just have a static declaration.

Link: https://www.analyticsvidhya.com/blog/2018/11/introduction-text-summarization-textrank-python/

# Mar 23, 2022
The major issue that the project is facing is the abnormal sentence structure of legal documents. The sentences are typically written with extra uses of punctuation, returns, and weird spacing. This presents issues for typical tokenizers as these tend to be built for normal sentences in enviornments like news articles, books, papers, etc. As such, this obviously causes errors in the resulting tokenized sentences.

The plan is to observe how casual tokeizers implement these senetnces and how they return punctuation, and then try a myriad of niche user-created PyTorch/Tensorflow legal-specific BERT tokenizers. These will be compared against one another, mixed, and ultimately we will decide the best possible match, then observe its performance within typical summarizers like TextRank, and observe both extractive and abstractive summarizers.
