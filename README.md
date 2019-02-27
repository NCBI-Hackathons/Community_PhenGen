# UPWARD: Uniting People Working Against Rare Diseases

*Table of Contents*

1. [**Background**](https://github.com/NCBI-Hackathons/Community_PhenGen#background)
2. [**Methods**](https://github.com/NCBI-Hackathons/Community_PhenGen#methods)
3. [**Results**](https://github.com/NCBI-Hackathons/Community_PhenGen#results)
4. [**Members**](https://github.com/NCBI-Hackathons/Community_PhenGen#members)
5. [**Documentation**](https://github.com/NCBI-Hackathons/Community_PhenGen#documentation)

### Background:
Porphyria is a group of eight inherited genetic disorders that arise when the body is unable to synthesize heme used to transport oxygen throughout the body. This negatively affects the skin and/or nervous system causing symptoms including extreme abdominal and chest pain, skin blistering, vomiting, confusion, constipation, fever, high blood pressure, and possibly leading to paralysis, low blood sodium levels, and seizures.

Porphyria is divided into two main types, acute and cutaneous, depending on the most commonly experienced symptoms. Acute Porphyrias typically present with attacks of symptoms, like intense abdominal pain or skin blistering, which become more severe over several days. Cutaneous Porphyrias may result in skin blistering, redness, scarring, and pain when exposed to the sun.

Likely affecting 1 to 100 people in every 50,000, Porphyria is a rare disease which on average takes 10-15 years to diagnose following the onset of symptoms. Once Porphyria is recognized diagnostic testing can be performed via blood, urine, stool and genetic testing.

*Data-driven discovery of rare disease determinants*

We are creating a program that will pull out all pathogenic or likely pathogenic Porphyria SNPs that are currently included on chips used for some common direct to consumer genetic/ancestry tests. This program can help us identify whether people who run their raw data through a database such as Promethease may find that they have a pathogenic or likely pathogenic SNP in any of the Porphyria genes.

Collecting the experiences of people who are identified from the general population in this fashion would be valuable to find out how they are following up with this information. Although most of these individuals will never develop symptoms (due to the low penetrance of these genes), it may prove useful to see if these individuals would enroll in future studies trying to compare those with latent and active porphyria in order to identify modifying genes and environmental factors that contribute to the phenotype. Furthermore, some of these results are expected to be false positives and this might allow the participants to access diagnostic testing and verify their genotype.

One possible way to recruit these individuals would be to add a link to the research database (and study consent) on SNPedia for each of the pathogenic variants of interest. To our knowledge, nobody has tried to recruit in this fashion and it may work because people who use these databases to interpret their raw data are likely to be interested in additional information and therefore may be willing to participate in research studies.

### Methods:

![flowchart](https://github.com/NCBI-Hackathons/Community_PhenGen/blob/master/DDDDD.png)

*Implementation*

To build a database of pathogenic or likely pathogenic SNPs we have sourced rsid information from the Illumina OmniExpress & Illumina GSA microarray chips (that Ancestry and 23andMe use respectively to carry out the DNA analysis) and filtered out genes using the NCBI ClinVar database to yield an output of Porphyria genes and their associated rsid, the SNP location, and level of pathogenicity. This will be combined with a database containing phenotype, genetic and symptom information of people with Porphyria and their family to try to capture data on asymptomatic people.

We are collecting a healthy human population’s consumer genomics raw data into a no-sql database. We built a HIPPA compliant human subject metainformation database in the next iteration of the development. Our system currently consists of a cloud database built upon MongoDB Community Edition, and a web server run through NGINX. The entire system is containerized and orchestrated by [Docker Compose](https://docs.docker.com/compose/), and can be generated by using two lines of code.

HIPPA compliance is satisfied by:

- Authentication: securely authenticate user access
- Authorization: assign user roles and privileges
- Auditing: maintain a CRUD log
- Encryption: TBD 

*Operation*

  **Requirements:** The only requirement to build this system is having [Docker](https://docs.docker.com/install/) and [Docker Compose](https://docs.docker.com/compose/install/) installed on your machine.
  
  **Running:**
  
  - clone this repository: `git clone https://github.com/NCBI-Hackathons/Community_PhenGen`
  
  - And start Docker containers: `cd Community_PhenGen && sudo docker-compose up`
  
  - In order to change security settings for the database, you need to change [these lines](https://github.com/NCBI-Hackathons/Community_PhenGen/blob/f6c0638d409b9ab5619b2db9961c84d259fc5c62/docker-compose.yml#L13-L15) from the source code.

### Results:

[DDDDD Website: You can help](http://www.raysjianglab.org/DDDD.php)

### Members:
Rays Jiang - [ray-jiang](https://github.com/ray-jiang) - Jiang2@health.usf.edu 

Renee Fonseca - [reneemf](https://github.com/reneemf) - reneefonseca@mail.usf.com

Minh Pham - [minhhpham](https://github.com/minhhpham) - minhpham@mail.usf.edu 

Deborah Cragun - dcragun@health.usf.edu 

Luis Tañon Reyes - [luistanonreyes](https://github.com/luistanonreyes) - luistanon@mail.usf.edu

Alex Dean - [deansmacked](https://github.com/deansmacked) - daviddean@health.usf.edu

Krishna Sharma - [ksharma1205](https://github.com/ksharma1205) - sharmak@mail.usf.edu

### Documentation:
