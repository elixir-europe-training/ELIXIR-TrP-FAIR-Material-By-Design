!!! success "Learning Outcomes"

    - Define training metadata
    - Discuss the importance of training metadata
    - Register training metadata in TeSS manually

## What is metadata

Most likely, you have already used metadata without even noticing it!
If I'm very practical I could tell that **Metadata** is just data used to describe other **Data**. Metadata should, however, live independently. The metadata has the function of describing and defining parameters that will make easier to find and compare other similar data.

Let me try to put in an example to make it easier:

_You look at a can (data) of a new beverage and later comment this with a friend who wants to know more. You do not remember the name (metadata) of the beverage, but you tell your friend about the height and colours of the can (metadata). Your friend quickly realises what that new beverage is as she has already tried it out._

Example from [FAIR handbook (chapter 04)](https://elixir-europe-training.github.io/ELIXIR-TrP-FAIR-training-handbook/chapters/chapter_04/), by [FAIR handbook working group](https://elixir-europe-training.github.io/ELIXIR-TrP-FAIR-training-handbook/contributor_list/). [CCBYSA 4.0 license](https://github.com/elixir-europe-training/ELIXIR-TrP-FAIR-training-handbook/blob/main/LICENSE.md)

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

## Schemas and Bioschemas

Bioschemas is a collaborative effort supporting metadata schemas to describe types relevant in the Life Sciences domain (e.g., Gene and Protein) and providing guidelines (known as profiles) on how to use general-purpose types offered by Schema.org (e.g., Dataset or Learning Resource). Schema.org 2 is also a collaborative effort providing cross-domain types with the purpose of adding structured markup to web pages so web search engines understand better what they are about.

GOBLET and ELIXIR have worked together on the subject of metadata for training materials under a community-based project umbrella, namely Bioschemas.

Many training related resources will include pages describing tutorials or courses. As such, they are marked up using the following three profiles:

    TrainingMaterial: A profile describing training materials in life sciences, it can be used on its own (as it happens with the Bioschemas tutorials) or in combination with a CourseInstance.
    Course: A profile describing a course from a generic point of view, i.e., the learning objectives of a course rather than where and when it is delivered.
    CourseInstance: A profile describing a particular instance of a course, i.e., an edition of a course that is scheduled for specific dates and happening in a specific location (that of course can be online or on-site, virtual or real).

Note that the CourseInstance profile is used in tandem with the Course profile, i.e., a CourseInstance does not exist without a Course but a Course can exist without a CourseInstance (there are no current offerings of the course).

TODO: add image (see Patricia)

## TeSS 
- TeSS (short version) and Course Metadata 

    - To manually register a training session/event

    - To manually register the training material

    - Use the schema.org validator to inspect the TeSS 







