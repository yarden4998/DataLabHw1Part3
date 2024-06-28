
# Data Analysis and Visualization Lab, HW1 Q3


## 🌟 Overview

We will explore the capabilities of Pinecone VectorDB and implement a basic Retrieval-Augmented Generation (RAG) pipeline. The goal is to enhance the performance of a standard Question Answering (QA) model by leveraging relevant documents from a vector database

## 🚀 Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo

2. **API Keys**
Place your Cohere API key in chohere_api_key.txt.
Place your Pinecone API key in pinecone_api_key.txt.

## 🔧 Usage

### 📚Embedding and Indexing Data
#### Embedding Dataset:
Utilize Sentence Transformers to embed text data from a specified dataset (fancyzhx/dbpedia_14 in this case).

#### Creating Pinecone Index:
Set up a Pinecone vector database to store embeddings.

### 🤖Querying Using Cohere's Chat API
#### Query Without Source Knowledge:
Directly query Cohere's API using a specified question.

#### Query With Source Knowledge:
Augment the query with top results from the Pinecone index and then query Cohere's API.

### 📝Example Queries
#### Query 1:

"In what year did Abbott of Farnham E D Abbott Limited close its operations?"

**Response without source knowledge:** 1991

**Response with source knowledge:** 1972

**Source:**

* Abbott of Farnham E D Abbott Limited was a British coachbuilding business based in Farnham Surrey trading under that name from 1929.A major part of their output was under sub-contract to motor vehicle manufacturers. Their business closed in 1972.
* Donald Healey Motor Company Limited was a British car manufacturer.
 * Witcomb Cycles formerly known as Witcomb Lightweight Cycles is the trading name of the Witcomb Trading Company. It was a British company based in Deptford South London specialising in custom handmade steel bicycle frames. The company was founded in 1949 by Ernie Witcomb and his wife Lily. The London shop closed in May 2009.

#### Query 2:

"When did Q-workshop establish its official website and online store?"

**Response without source knowledge:** Q-workshop established its official website and online store in 2012.

**Response with source knowledge:** Q-workshop established its official website and online store in 2005.

**Source:**

* Q-workshop is a Polish company located in Poznań that specializes in designand production of polyhedral dice and dice accessories for use in various games (role-playing gamesboard games and tabletop wargames). They also run an online retail store and maintainan active forum community.Q-workshop was established in 2001 by Patryk Strzelewicz – a student from Poznań. Initiallythe company sold its products via online auction services but in 2005 a website and online store wereestablished.
* I-innovate (UK) is a London-based independent record label that diversified from video production into music management from 2009. I-innovate was founded by Najero Okenabirhie in 2008. I-innovate work with freelance directors marketers and artists in music and graphic design providing ad hoc services for clients labels and music professionals.
* Victor Company of Japan Ltd (日本ビクター株式会社 Nippon Bikutā Kabushiki-gaisha) TYO: 6792 usually referred to as JVC is a Japanese international consumer and professional electronics corporation based in Yokohama Japan. Founded in 1927 the company is best known for introducing Japan's first televisions and for developing the Video Home System (VHS) video recorder. In 2008 JVC merged with Kenwood Corporation to create JVC Kenwood Holdings.

#### Query 3:

"In what year did The Unsigned Guide transition from a printed directory to an online-only resource?"

**Response without source knowledge:** 2013

**Response with source knowledge:**  2011.

**Source:**

* The Unsigned Guide is an online contacts directory and careers guide for the UK music industry. Founded in 2003 and first published as a printed directory The Unsigned Guide became an online only resource in November 2011.
* SCAN Health Plan (SCAN) is a not-for-profit health plan founded in 1977 and based in Long Beach California. The organization serves more than 110000 people with Medicare in Kern Los Angeles Orange Riverside San Bernardino San Diego and Ventura counties California and Maricopa county Arizona. The company also offers a health plan for Medicare and Medicaid-eligible individuals as part of the state’s long term care program in Maricopa county.
* Cavity Search Records is a record label based in Portland Oregon formed in 1992 by Christopher Cooper and Denny Swofford. It is known for producing debut records by bands Hazel Heatmiser The Helio Sequence King Black Acid and Richmond Fontaine along with debut records for singer-songwriters Danny Barnes Saul Conrad Pete Krebs and Elliott Smith.

##  📊Results and Conclusions 
Our findings demonstrate the utility of RAG. Answers without the data source were consistently inaccurate, while with the data source, they were consistently accurate.
