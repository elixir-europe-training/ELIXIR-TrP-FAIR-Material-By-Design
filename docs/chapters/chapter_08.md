--- 
Lead: Elin 
Duration: 110 min
Title: Releases and use of unique identifiers
To cover: 
- What is a DOI and why is it useful for training materials 
- Different strategies for adding DOIs for training materials
- Connecting a GitHub repository with Zenodo to assign a DOI
- Use releases in GitHub to make new versions  
To Reuse:
- chapter 10 FAIR trianing handbook -> https://elixir-europe-training.github.io/ELIXIR-TrP-FAIR-training-handbook/chapters/chapter_10/
---

!!! success "Learning Outcomes"

    - Compare different strategies for unique identifiers for training material
    - Create versioned DOI for training material in a GitHub repository 


## 1.1 Unique identifiers for training materials (20 min)
- What is a unique persistent identifier?

A persistent identifier is a type of metadata that uniquely tags a digital object. 
 - leads to a landing page with the listed digital object and its metadata. Actual access to the digital object from this page might be restricted. 

- Why is it useful for training materials?
Help distinguish between :
- different materials
- different versions of the same material

"I attended this ELIXIR course on data management practices which was really good, you should have look at it" 
-- screenshot of 


-  Versioning of DOIs

- Explore different strategies
    -   group exercise, presenting strategies to each other



## 1.2 Selecting a strategy for unique identifiers (40 min)
-   DOI for presentations


!!! checklist "Case Studies of Using PIDs in Training"

    Read through the real world examples of using PIDs in Training from [chapter 5](https://elixir-europe-training.github.io/ELIXIR-TrP-FAIR-training-handbook/chapters/chapter_05/) in the the FAIR Training handbook. 

    - Summarise the strategy used in each use case
    - What is the main benefit with each strategy?
    - Are there any drawbacks with each strategy?


    ??? abstract  "Case 1 - Assigning a unique DOI combined with ORCID for each event in a community"

            
        At [Australian BioCommons](https://www.biocommons.org.au/), training materials from webinars and workshops are shared via a dedicated [Zenodo community](https://zenodo.org/communities/australianbiocommons-training/). BioCommons chose to use Zenodo to share training materials because they do not have a repository of their own, and Zenodo has established ways of managing metadata, DOIs and versioning. It is also widely used in the scientific community.

        For each event, a Zenodo record is created that includes detailed metadata, new training materials and links to previous materials that were reused as part of the training (Figure 1).


        Two types of PIDs are used when sharing materials from our events.

        * DOIs - Zenodo automatically assigns a DOI to the event. DOIs are also used when linking to related materials to ensure that there is no ambiguity about which materials were used.

        * ORCID - Trainers’ ORCIDs are used to ensure that they get the credit for their efforts and to make it clear who participated in the event.

        <figure>
            <img src="../../assets/images/FTH-zenodo_highlighting_pids.png"
            width="500" alt="Screenshot of an Australian BioCommons training record in Zenodo highlighting the use of ORCIDs and DOI"/>
        </figure>

        **Figure 1:** The Australian BioCommons collates materials from their events and shares them via Zenodo where they are assigned a DOI and authors are identified via their ORCIDs. [View this record on Zenodo.](https://zenodo.org/doi/10.5281/zenodo.5781811)

    
    ??? abstract "Case 2 - Creating virtual collections of training materials and assigning own PIDs"

        For [CLARIN](https://www.clarin.eu/), a training event usually consists of slides, handouts, a GitHub page, video tutorials, language resources, datasets and/or tools. The slides and handouts are published on the event web page, while the video recordings of the presentations are published on the CLARIN YouTube channel. In addition, the language resources and tools used during the training are stored in the CLARIN national repositories, with a **unique** identifier assigned by the institution and can be cited.


        One solution to have a PID assigned to all the materials used during one training event is to create a virtual collection in the CLARIN [Virtual Collection Registry](https://collections.clarin.eu/public?7). A virtual collection is a coherent set of links of digital objects that can be easily created, accessed and cited with the help of **unique identifiers**, for example, a DOI. The links can originate from different archives. [Here](http://hdl.handle.net/11372/VC-1033) is an example of a virtual collection created for a hands-on tutorial on transcribing interview data

        <figure>
            <img src="../../assets/images/FTH-clarin_image1.png"
            width="500" alt="Screenshot of CLARIN metadata from workshop tutorial SSHOC"/>
        </figure>
        **Figure 2:** Example of a training collection in the CLARIN Virtual Collection Registry that has been assigned a persistent identifier.

        <figure>
            <img src="../../assets/images/FTH-fig3-chap5.jpg"
            width="500" alt="Screenshot 'zoom'  of CLARIN metadata from workshop tutorial SSHOC, and citation"/>
        </figure>

        **Figure 3:** Example of a BibTeX citation in the CLARIN Virtual Collection Registry.


        Other practices that the trainers in the CLARIN community have adopted are:

        - First, depositing the training materials together with the datasets in their CLARIN national data repository. See example:[Archilochus of Paros: Elegiac Fragments - XML Archive](http://hdl.handle.net/20.500.11752/OPEN-537). The advantage of using this path is that the authors can add more extensive metadata to describe their materials. 
        - Second, depositing the training materials on Zenodo. See example: [Introduction to Speech Analysis](https://doi.org/10.5281/zenodo.5506969).  In this case, **related identifiers** are included that lead users to the main platform where the course is stored and maintained. 
        - Third, adding the metadata of the training materials to the SSHOC Open Marketplace, see example: [Jupyter notebooks for Europeana newspaper text resource processing with CLARIN NLP tools](https://marketplace.sshopencloud.eu/training-material/duVII1). In this case, the Marketplace does not assign any unique identifiers, but the authors can identify themselves via their ORCID and can suggest a citation format for their collection.

    ??? abstract "Case 3 - Creating virtual collections of training materials and assigning own PIDs"

        The [Dutch Techcentre for Life Sciences](https://www.dtls.nl/) (DTL) has a [Zenodo community](https://zenodo.org/communities/dtl/?page=1&size=20) to upload presentations and course materials. DTL has chosen to give separate DOIs for individual, often topical, elements of a course. An example is the [Helis Academy FAIR Datastewardship Course](https://www.aanmelder.nl/fair-data-stewardship-2021), a course of 6 half days. 

        Providing a separate DOI has the following advantages: It is easier to mix and match different modules as part of a learning path, i.e. different combinations of our training modules can be made for the various target audiences, tailored to that specific purpose. When updating or revising a single module, it is more convenient to have that module as a separate entity with its own DOI, in order to easily keep track of the versions of different modules.

        At the level of the full course, we have chosen to use ELIXIR TeSS as the registry. Links to our training event details and training materials can be found [here](https://tess.elixir-europe.org/events/helis-course-fair-data-stewardship).

        <figure>
            <img src="../../assets/images/FTH-fig4-chap5.png"
            width="500" alt="Screenshot DTL data stewardship course DOIs view"/>
        </figure>
        **Figure 4:** Example from the DTL Helis FAIR Data Stewardship Course with separate DOIs per topic. See more [here](https://www.aanmelder.nl/fair-data-stewardship-2021).


        <figure>
            <img src="../../assets/images/FTH-fig5-chap5.png"
            width="500" alt="Screenshot Zenodo page for day 1 course from DTL"/>

-   DOI for repositories and releases

-   Individual/pair-wise work for their own context "at home"

## 1.3 Implementing your strategy (50 min)

Now we will use Zenodo sandbox to create DOIs for our training material project from this course. This turtorial will guide you through the steps of creating a Zenodo record for your GitHub repository that will be automatically versioned. Upon creation of a new realse of your repositiry, a new DOI will be issued that is linked to the original one. You need to have an ORCID and a GitHub account before we get started.


??? success "Get an ORCID iD"

    Create your ORCID iD by [registering](https://orcid.org/register) at the [ORCID website](https://info.orcid.org/researchers/)


??? success "Get a GitHub account"

    Create your GitHub account by [signing up](https:/github.com)

- Login/create a Zenodo account in Zenodo sandbox (Easiest via GitHub)
- Link the repo and the Zenodo account from Zenodo)
- Create an item
- Add DOI badge to repo (make sure to use DOI for all versions)
- Create a new release (the release notes are the description by default)
- Update TeSS


