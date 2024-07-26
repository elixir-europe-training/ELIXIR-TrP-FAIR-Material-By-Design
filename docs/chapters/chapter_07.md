!!! success "Learning Outcomes"

    - LO1
    - LO2
    - LO3



## First subtopic

- What is metadata and why is important

https://elixir-europe-training.github.io/ELIXIR-TrP-FAIR-training-handbook/chapters/chapter_04/ 

Introduction to metadata

Metadata can be defined as data used to describe other data. That other data is complete on its own even without the metadata; however, the metadata makes it easier, for instance, to quickly grasp what that other data is about and to establish some common parameters that can be used to find and compare similar data, even if you have no access to that other data. As examples might be easier to grasp than definitions, let’s have a look at a couple of metadata examples:

    You look at a can (data) of a new beverage and later comment this with a friend who wants to know more. You do not remember the name (metadata) of the beverage, but you tell your friend about the height and colours of the can (metadata). Your friend quickly realises what that new beverage is as she has already tried it out.
    You can read, enjoy and learn from a book (data) even if you do not know the title, the author, or the date it was printed (metadata). However, if you really like that book and know the name of the author, you can also find other books by the same author.
    You look for a film (data) in your preferred browser. As you know the title (metadata) you can easily find not only the film (access is restricted to those renting the film) but information about the director and the actors, and even a summary of the plot (more metadata).
    You are interested in finding concerts happening during summer. You go to your preferred browser and use some keywords (metadata) to find some concerts close to your city.

Most likely, you have already used metadata without even noticing it!

While the first example involved only people, the other three involved people and machines. When we want to communicate with other people, we use words, either orally or written and thanks to the common knowledge of the used language, e.g., English, we can understand each other. A sentence like ‘the title of this chapter is “Using metadata to describe training materials” ‘ is clear for us, but while free text is enough for humans, machines need more structured data (and metadata) to communicate with each other. The sort of structured metadata we use to describe training materials looks like a sentence with a subject, a predicate, and an object, with the main subject being our training material. The sentence above would for example look like: thisChapter (subject) - hasTitle (predicate) - “Using metadata to describe training materials”. Further information about how we communicate with machines and how machines communicate with each other is an exciting subject, but it is outside the scope of this book. If you are interested, we offer some additional information in Section Further reading about structured metadata.


- Ontology (authors/contributors/…)

Dictionary
Definitions from Oxford Languages · Learn more
ontology
a set of concepts and categories in a subject area or domain that shows their properties and the relations between them.
"what's new about our ontology is that it is created automatically from large datasets"

Controlled vocabulary

## Bioschemas

GOBLET and ELIXIR have worked together on the subject of metadata for training materials under a community-based project umbrella, namely Bioschemas. Bioschemas 1 is a collaborative effort supporting metadata schemas to describe types relevant in the Life Sciences domain (e.g., Gene and Protein) and providing guidelines (known as profiles) on how to use general-purpose types offered by Schema.org (e.g., Dataset or Learning Resource). Schema.org 2 is also a collaborative effort providing cross-domain types with the purpose of adding structured markup to web pages so web search engines understand better what they are about.

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







