!!! success "Learning Outcomes"

    - Discuss the importance of training metadata
    - Define what is training related metadata
    - Register training events and materials in TeSS manually
    - Create a JSON object as basis for automated ingestion of metadata into TeSS

## 7.1 Presentation

Here you can find the presentation for this session:
<iframe src="https://docs.google.com/presentation/d/1ZcFJpbXtxT4Qa6wgffV_oEX8_cZfzM8B-VlMH0Cff0I/preview" width="640" height="360" allow="autoplay"></iframe> 

## 7.2 What is metadata and its structure

Most likely, you have already used metadata without even noticing it!
If I'm very practical I could tell that **Metadata** is just data used to describe other **Data**. Metadata should, however, live independently. The metadata has the function of describing and defining parameters that will make easier to find and compare other similar data.

Let me try to put in an example to make it easier:

_You look at a can (data) of a new beverage and later comment this with a friend who wants to know more. You do not remember the name (metadata) of the beverage, but you tell your friend about the height and colours of the can (metadata). Your friend quickly realises what that new beverage is as she has already tried it out._

Example from [FAIR handbook (chapter 04)](https://elixir-europe-training.github.io/ELIXIR-TrP-FAIR-training-handbook/chapters/chapter_04/), by [ELIXIR training platform](https://elixir-europe-training.github.io/ELIXIR-TrP-FAIR-training-handbook/contributor_list/). [CCBYSA 4.0 license](https://github.com/elixir-europe-training/ELIXIR-TrP-FAIR-training-handbook/blob/main/LICENSE.md)

As said before and you can see in the example, the metadata helps describing the data, this will be important in the data retrival, meaning - people can more easily find it - and also in the comparison with similar data, in our case other training materials.

But looking into another example from the chapter 04 from the FAIR handbook:

_You look for a film (data) in your preferred browser. As you know the title (metadata) you can easily find not only the film (access is restricted to those renting the film) but information about the director and the actors, and even a summary of the plot (more metadata)._

In this example includes not only humans, but also machines. You can lookup in the brounser and find a lot of information about the movie, nonetheless is most probably that you can only watch it if you pay a fee or have a streaming account. The metada of the movie that is retrieved might look like has a lot of free text, what is great for humans, but machines need more structure for better functioning

The sort of structured metadata we use to describe training materials will look a like having a key concept followed by a description. Ideally this descriptions as much as the key concept will use therms with clear meanings. For example:

Title: Course Title
Author: Name FamilyName
Level: Begginers

As part of being clear and machine redable, the more we focus in Ontology, the more we can achieve. Do you know what is an ontology?

Ontology according to the definition from Oxford Languages is a set of concepts and categories in a subject area or domain that shows their properties and the relations between them. For example, we can look into the controled vocabulary for _pants_, this is one concept that has propeties and relations:

| Pants        | Categories |        |       |
| -----------  | -----------|--------|-------|
|**Adults**    | Casual     | Sports | Dress |
|**Children**  | Dress      | Play   |       |

You have *Pants* as a term, and it can be categorized for *Adults* and *Children* and within them *Casual*, *Sports*, *Dress* and *Play*. This way the information is structures and can easily be identified by machines and comapring and finding similar things will be easier, like when you filter for searching in a online clothes shoping. 

But for training, as expected, we have other categories, and they are defined with Schemas.org and Bioschmas.org

## 7.3 Schemas and Bioschemas

Bioschemas is a collaborative effort supporting metadata schemas to describe types relevant in the Life Sciences domain (e.g., Gene and Protein) and providing guidelines (known as profiles) on how to use general-purpose types offered by Schema.org (e.g., Dataset or Learning Resource). Schema.org 2 is also a collaborative effort providing cross-domain types with the purpose of adding structured markup to web pages so web search engines understand better what they are about.

GOBLET and ELIXIR have worked together on the subject of metadata for training materials under a community-based project umbrella, namely Bioschemas.

Many training related resources will include pages describing tutorials or courses. As such, they are marked up using the following three profiles:

    TrainingMaterial: A profile describing training materials in life sciences, it can be used on its own (as it happens with the Bioschemas tutorials) or in combination with a CourseInstance.
    Course: A profile describing a course from a generic point of view, i.e., the learning objectives of a course rather than where and when it is delivered.
    CourseInstance: A profile describing a particular instance of a course, i.e., an edition of a course that is scheduled for specific dates and happening in a specific location (that of course can be online or on-site, virtual or real).

A training event in TeSS is described by the BioSchemas profile CourseInstance, while the schema.org Event profile is something different. So, let’s start this session pointing out a few differences of each profile:

An unique event such as a congress, symposium, webinar will be classified using the Event profile in Schemas.org, while the Bioschemas Course profile is attached to a unit of teaching that typically lasts one or more academic terms, is led by one or more instructors (teachers or professors), and has a fixed roster of students. A course usually covers an individual subject. Such a course will be linked to several course instances that happen at different moments, locations and might be also subjected to updates and small differences in the material. A course and/or course instance should be linked to a course material, that represents the content of this course/course instance. In TeSS, though, courses and courses instances are in called Event in the interface, while this is not the same as the profile in schemas.org. It works to filter among all courses, webinars, symposia, congresses etc.

Note that the CourseInstance profile is used in tandem with the Course profile, i.e., a CourseInstance does not exist without a Course but a Course can exist without a CourseInstance (there are no current offerings of the course).

Such an event in TeSS is a link to a single training event sourced by a provider along with description and related meta information (e.g. date, location, audience, ontological categorization, keywords, etc.). 

Training events in TeSS can be added manually or automatically harvested from a provider's website. Here is the procedure to register for training events manually.

![screenshot for login page](../../assets/images/rhh0rv5.png)

## 7.4 Discover events and materials in TeSS

### Scenario: Searching for training material in TeSS

Training resources (both events and materials) may be searched in TeSS in several ways. If you are on the main page of TeSS, a general search can be performed based on keywords, which will return separate lists of events and materials. Alternatively, events or materials can be searched for independently of each other. This second approach allows more precise filtering on several parameters (e.g., event type, country, and target audience) alone or in combination.

![screenshot for TeSS page with search box](./../assets/images/GxGphHo.png)

In this protocol, we provide examples of searches for specific events or materials. Be aware that by searching for events, the standard search returns only future events. If you want to include past events, you need to click the **Show past event** button. 

Please navigate to [TeSS](https://tess.elixir-europe.org) and follow the steps shown below.

1. Select Materials in the top menu.
2. **Search for** ‘Single-cell’ as the keyword in the search text box on the right side of the page. **You can click on the magnifier icon or press Enter**.
3. Click on 'Filters' if you do not see this side menu due to your browser being non-fullscreen.
4. On the side menu, scroll down to the Difficulty facet. We will select the Intermediate.
6. As a result, you get the list of materials about single-cell data analysis with intermediate difficulty level.

At any time you may remove any of the filters you applied to reduce stringency of your search.

Please proceed to the next step to see the results.

At any time you may remove any of the filters you applied to reduce stringency of your search.

In September 2024, we found 7 past materials with this search query.  

Have a look at the URL to understand how you could query TeSS via the API.

https://tess.elixir-europe.org/materials?difficulty_level=Intermediate&q=Single-cell

Let's have a look at the documentation of the API: https://tess.elixir-europe.org/api/json_api#tag/events

Here you see all the query parameters. In our query, we have been using several of these parameters and concatenated them.

1. First, we used the free text query parameter `q` and set it to `Single-cell`. 
2. Third, we used the `difficulty_level` parameter and set it to "Intermediate". Note that you need to replace the space by a `+` sign. 

If you would like to get the material from the Galaxy training network GTN, too, you'd need to add yet another query with `content_provider=GTN`.

To get the full query, you need to concatenate all the individual queries with an ambersand `&`. 

## 7.5 Show your events and materials in TeSS 

In order to be able to register resources in TeSS you need to log in the registry. The following steps are specific for the login procedure with the Life Sciences Account. Alternatively, you can use another existing account like Google, Apple or an ORCID. In this case you will be redirected to the respective login portal.

### Scenario: Log into TeSS using an institutional account

**We will not be able to provide a detail procedure for all the federated authentication mechanisms here. Try the example below.**

1.	Open your browser and go to the development version of [TeSS](https://dev.tess.elixir-europe.org/). We use the sandbox for educational purposes here.

2.	Click the “Log In” dropdown button on the top-right corner of the page.

3.	To log in using your institutional account, choose Log in with LS Login from the dropdown menu
You will be redirected to the LifeScience RI authentication page (Fig. 1).

![screenshot for login page](../../assets/images/6dXdfgu.jpg "Figure 1")

4.	Start typing the name of your own institution, for instance ‘VIB’, into the text box then choose the appropriate option that appears and proceed with your usual institutional login procedure (Fig. 2). 

![screenshot for login page](../../assets/images/l5mQUND.png "Figure 2")

5. You should now be logged into TeSS. Once successful, you should be taken to the TeSS Welcome page with a message stating “Logged in successfully.”  You should also see your username in the top bar of the page, which you can click to view and edit your TeSS profile.

![screenshot for login page](../../assets/images/meCcJjO.png "Figure 3")

6.	Check all the fields in your user profile are correct and click the “Update Profile” button.
You will also see a button to log out of TeSS.

### Scenario: Registration of a content provider in TeSS

Training resources (events and materials) may be added to TeSS to reach bigger audiences, increase impact and bolster event attendance. Registering events and training materials makes them more findable in a variety of ways to various user bases. TeSS features content providers which are entities (such as academic institutions, non-profit organisations, portals etc.) that provide training materials of relevance to life sciences and ELIXIR. In order to have a training event automatically harvested in TeSS, a content provider has to be registered first. It also adds visibility to content providers. Here is the procedure to register a new content provider in TeSS.


1. Login to TeSS at https://dev.tess.elixir-europe.org.

2. To register a content provider, click on the Providers menu.

3. Click on “+ Register content provider”. You will be directed to a form type of page.

4.  As an example, we will create the content provider NanoCommons. Enter “NanoCommons“ in the Title field.

5. In the URL field, enter the URL of the content provider, which is “https://www.nanocommons.eu/” in our example.

6. Enter “Jean Dupont” as a contact person in the Contact field.

7. In the subsequent field Description, provide general information and relevant context about the content provider in the form of short text.

This field supports markdown syntax.

Here is one example: “NanoCommons will deliver a sustainable and openly accessible nanoinformatics framework (knowledgebase and integrated computational tools, supported by expert advice, data interpretation and training), for assessment of the risks of NMs, their products and their formulations. NanoCommons combines Joint Research Activities to implement the nanoinformatics Knowledge Commons, Networking Activities to facilitate engagement with the research community, industry and regulators, and provision of funded Access to the nanoinformatics tools via funded calls for Transnational Access.”

8. Enter a image to have a **visual representation of the content provider**. The image can be added by URL of the image location or by uploading an image.

![screenshot for login page](../../assets/images/qyOSDyb.png)

9. Enter the type of the content provider in the Type field. You can choose ‘Project’, ‘Organisation’ or ‘Portal’.

10. In the field Approved Editors, You can add more than one **registered** user as Approved Editor. Selected users can be removed by clicking on the red cross.

11. In the field Keywords, enter the keywords related to the content provider.

12. Select an associated ELIXIR node if applicable. In this example, there is no direct association with ELIXIR nodes, so we leave it empty.

13. Confirm the creation of the content provider by clicking on ‘Register content provider’.

### Scenario: Manual registration of a training event in TeSS

1. Login to sandbox of TeSS at https://dev.tess.elixir-europe.org as outlined above.

2. To register for a training event, click on the Events menu.

3. Click on “+ Register event”. As an example, we use an RNAseq training event.
You will be directed to a form type of page. 

![screenshot for login page](../../assets/images/appDpje.png)

4. Select that Type at the beginning of the form since we enter a face-to-face event.
If your event is online, choosing the option "Online" which will modify the form to fit that type of event i.e. no address field has to be filled in. 

5. In the Title field, enter the Title of the event, which is “Your course about FAIR training” in our example.

6. The optional Subtitle field can be filled in case you’d like to specify more context on the event, like “Spring edition” of a regularly repeated course.

7. In the URL field, enter the URL where the announcement and registration of the training event can be found. In our example, please use the link to the cloned github-based course template.

8. In the subsequent field Description, provide general information and relevant context about the training event in the form of short text, like in our example: “Be as precise as possible when describing your course.”
This field supports markdown syntax.

9. Specify the start date and door time of the event in the field Start via the pop-up Date and Time Picker. In our example, the event starts on the 29th of September 2024.

10. Specify the end date of the event in the field End via the pop-up Date and Time Picker. Our example event will end on the 4th of October 2024.

11. In the field Timezone, enter the time zone of the location where the event will occur and pick the one that applies. In our example, we select ‘(GMT:+01:00) Amsterdam’ since the event takes place in Leuven, Belgium.

12. In the field Duration, indicate how long the event will last in hours, days, whatever applies best. Enter ‘2 days’ for our example.

13. In the field Prerequisites, enter which prerequisites are necessary to follow the training event. For example, write “Background knowledge of NGS data formats and the first steps in the analysis workflow (fastqc -> bam files). If you are a newbie in the field, you have to follow the NGS introduction training first. Experience in R programming is highly recommended. If you never worked with R, you should attend the R introduction training first.” This field supports markdown syntax.

14. In the field Learning objectives, list the learning objectives of the training event like you have defined before.

We recommend applying the Bloom hierarchy of cognitive skills to formulate the Learning objectives. For more detailed information about our pedagogical model, please browse to the course material of the ELIXIR Train the Trainer course https://github.com/TrainTheTrainer/ELIXIR-EXCELERATE-TtT This field supports markdown syntax. 

16. For the Address and related fields, enter the relevant information as
    
   -	Address: fill in the address by starting to type the address. Once you select an address, the Google maps view will be shown and the fields Venue, City, Region, Country and Postcode will be filled in automatically
   -	Venue: the venue of the event e.g. street
   -	City: the city where the venue is located
   -	Region: the region where the city is located
   -	Country: the country where the event will take place
   -	Postcode: the postcode of the venue

In our example, these are

   -	Herestraat 49
   -	Campus Gasthuisberg
   -	Leuven
   -	Flemish region
   -	Belgium
   -	3000

18. For the Eligibility field, there are three options you can choose from: First come first served, Registration of interest, By invitation. You could provide more than one eligibility type, if applicable. In our example, we enter First come, first serve.

19. Enter for example ELIXIR-Belgium in the Organiser field.
This field is a free text field.

20. Enter the name of the training coordinator in the contact field. 
Since this is also a free text field, one or more contact persons preferably with an email address can be added.

21. Start typing ‘VIB’ as the name of the host institution(s) in the ‘Host institutions’ field. 
You will get a dropdown menu to choose from. If your institution is not present in the menu, add it. Add as many as you’d like.

22. Enter ‘transcriptomics’ in the Keywords field.
You can start typing keyword(s) and you will get a list to choose from. Add as many as you want.

23. Enter ‘Life scientists researchers’ as Target audience. 
Start typing target audience types and you will get a list to choose from. Add as many as you want.

24. In the field Scientific topics, enter ‘Training’.
You can enter the appropriate scientific topics according to the EDAM ontology. In case you do not have a matching entry, you could use the keywords field.

25. For training, there might be not EDAM entries in the Operations field.
You can enter the appropriate operations according to the EDAM ontology. In case you do not have a matching entry, you could use the keywords field.

26. Add e.g. 20 as maximum number of attendants to the event in the field Capacity. 

27. Enter ‘Workshops and courses’ as Event type.
There are four options for the event type: Workshops and courses, Awards and prizegivings, Meetings and conferences, Reception and networking. You could provide more than one event type if applicable.

25. As Tech requirements, enter “github”. 
You can list here any technical requirement needed to follow the training event. Ideally, you also provide a link to the installation instructions. This field supports markdown syntax.

26. Enter ‘Certificate of attendance recognised by Doctoral School’ as the type of credit or recognition of attendance that will be delivered.

27. In the field External resources, search for tools which could be relevant. Once the tool has been found in bio.tools, click on the “+” sign to add it to the entry.
You can also associate policies, standards and databases (provided by FAIRsharing) with your training event. In each case, start typing keywords and a list of existing resources will be listed to select from (click on the “+” sign).

28. Select ‘Cost to non-members’ as Cost basis.
There are three choices: Free to all, Cost to non-members, Cost incurred by all.

29. Select ‘VIB Training’ as Content Provider. 
In case you do not find your organisation, please register it first as a Provider in TeSS. 

30. Search for ‘FAIR training’ in the Materials search box and select suggested training materials to associate with this course. Start typing keywords and a list of existing training materials will be listed to select from (click on the “+” sign).

31. Select ‘ELIXIR Belgium’ as a node from the downtown list. Select the node the organiser(s) belong(s) to.

32. Enter ‘VIB’ as Sponsors/Funders of your training event.

33. Click on the Add event button to finalize the manual registration.

### Scenario: Validate the metadata information of your entry

Validate the individual page with the [schema.org validator](https://validator.schema.org) by pasting the URL into the Fetch URL tab. The validation procedure will indicate if you have used non-existing properties of the Bioschemas profile. If error messages are returned, have a look at the troubleshooting section below.

Example: https://nanocommons.github.io/tutorials/enteringData/index.html

![screenshot for login page](./../assets/images/b369eIQ.png)

You will get the the HTML code of the web site on the left side and a list of type from schema.org. Open the entries on the left side to check on eventual error. 

How is this content embedded in the HTML page. It is called JSON-LD markup. 

Look for a script element with the attribute type="application/ld+json". This script element could be a child of the head element of the HTML page. This results in the following script HTML element.

```json
 <script type="application/ld+json">
  {
	"@context": "https://schema.org/",
	"@type": "LearningResource",
	"http://purl.org/dc/terms/conformsTo": { "@type": "CreativeWork", "@id": "https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE" },
	"name": "Adding nanomaterial data",
	"version": "0.9.3",
	"description": "This tutorial describes how nanomaterial data can be added to an eNanoMapper server using a RDF format.",
	"license": "https://creativecommons.org/licenses/by/4.0/",
	"keywords": "ontologies, enanomapper, RDF",
	"url": "https://nanocommons.github.io/tutorials/enteringData/",
	"provider": {
  	"@type": "Organization",
  	"name": "NanoCommons",
  	"url": "https://www.nanocommons.eu/"
	},
	"audience": {
  	"@type": "EducationalAudience",
  	"educationalRole": "Graduates"
	},
	"inLanguage": {
  	"@type": "Language",
  	"name": "English",
  	"alternateName": "en"
	},
	"author": [
  	{
    	"@context": "https://schema.org",
    	"@type": "Person",
    	"name": "Egon Willighagen",
    	"identifier": "https://orcid.org/0000-0001-7542-0286",
    	"orcid": "https://orcid.org/0000-0001-7542-0286"
  	}
	]
  }
</script>
```

### Scenario: Annotate your training material using the JSON object.

If you are using the G-suite setup, copy the JSON object of the [github template](https://github.com/vibbits/training_material_template/blob/main/README.md) which is located at the top of the README.md file. Paste the content from the clipboard to a text file (suffix .json), edit it in the g-drive and save it there.

If you are using the github setup, edit the JSON object of your cloned github template which is located at the top of the README.md file. You can verify the presence of the JSON-LD object with the schema.org validator using the rendered version of your course page.
