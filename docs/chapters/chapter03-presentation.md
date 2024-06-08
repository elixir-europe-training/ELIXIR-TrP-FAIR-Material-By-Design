<!--
title: "Liascript Presentations"

import: https://raw.githubusercontent.com/LiaScript/CodeRunner/master/README.md
        https://raw.githubusercontent.com/LiaTemplates/BeforeAndAfter/0.0.1/README.md

icon:   https://tess.elixir-europe.org/assets/elixir/elixir-tess-219b707c4912e9c46c917a24ce72b464ec9f2fd56ce03dbcee8b2f6b9ac98a44.svg

link:   https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css
        https://fonts.googleapis.com/css?family=Lato:400,400italic,700
        style.css

@runR: @LIA.eval(`["main.R"]`, `none`, `Rscript main.R`)

@JSONLD
<script run-once>
  let json = @0 

  const script = document.createElement('script');
  script.type = 'application/ld+json';
  script.text = JSON.stringify(json);

  document.head.appendChild(script);

  // this is only needed to prevent and output,
  // as long as the result of a script is undefined,
  // it is not shown or rendered within LiaScript
  console.debug("added json to head")
</script>
@end


link:   https://unpkg.com/leaflet@1.9.4/dist/leaflet.css
script: https://unpkg.com/leaflet@1.9.4/dist/leaflet.js

-->

# Training materials formats

This presentation will guide you through this session where we will touch on:

- different types of training materials and its re-usability
- 
- Image, video, and iframe embedding
- Elegant transitions and animations
- Printing to PDF via Liascript Exporter

...and much more

```json   @JSONLD
{
  "@context": "https://schema.org/",
  "@type": "LearningResource",
  "@id": "https://elixir-europe-training.github.io/ELIXIR-TrP-TeSS/",
  "http://purl.org/dc/terms/conformsTo": {
    "@type": "CreativeWork",
    "@id": "https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE"
  },
  "description": "TeSS, how can I help you? This is our interactive hands-on course about efficient use of the ELIXIR TeSS platform.",
  "keywords": "FAIR, OPEN, Bioinformatics, Teaching, TeSS",
  "name": "TeSS, how can I help you?",
  "license": "https://creativecommons.org/licenses/by/4.0/",
  "educationalLevel": "beginner",
  "competencyRequired": "none",
  "teaches": [
    "search events and material in TeSS via direct and faceted search",
    "add manually and automatically events and material to TeSS",
    "extract events and material from TeSS by using TeSS widgets"
  ],
  "audience": "training providers",
  "inLanguage": "en-US",
  "learningResourceType": [
    "tutorial"
  ],
  "author": [
    {
      "@type": "Person",
      "name": "Bruna Piereck"
    },
    {
      "@type": "Person",
      "name": "Olivier Sand"
    },
    {
      "@type": "Person",
      "name": "Alexander Botzki"
    }
  ],
  "contributor": [
    {
      "@type": "Person",
      "name": "Yasmine Maes"
    },
    {
      "@type": "Person",
      "name": "Finn Bacall"
    },
    {
      "@type": "Person",
      "name": "Munazah Andrabi"
    }
  ]
}
```

## Formats for training material

               --{{1}}--
******************
Welcome, everyone! Today, we’re going to embark on an interactive journey to explore the diverse landscape of training materials in life sciences. Our activity is designed to not only identify the various formats available but also to reflect on our personal preferences and the rationale behind them.

Activity Overview: We’ll examine different types of training materials, ranging from slides and videos to datasets and software. For each category, we’ll determine the possible formats they could take. Then, we’ll dive deeper to discuss which formats we predominantly use and, most importantly, why we prefer those over others.

This exercise will not only enhance our understanding of the material formats but also provide insights into our teaching methodologies. It’s a chance to share experiences, learn from each other, and possibly discover new ways to engage our audience.

So, let’s get started! Please go to to [the joint file](). As we proceed, I encourage you to think critically about the ‘why’—it’s the key to understanding our choices and improving our approach to training. Let’s have a productive session!

*********
           
![](../assets/images/03-activity-team.png)<!--
style = "width: 100px;"
-->
Activity: How many training materials formats can you list?

Identify possible formats for each type of material. Which format(s) do you mostly adopt? Why?

 | Material type | Possible format(s) | Format(s) you mostly use | Why? |
 | --- | --- | --- | --- |
 | slides |  |  | |
 | video |  |  | |
 | dataset |  |  | |
 | repository |  |  | |
 | exercises |  |  | |
 | VM/Container |  |  | |
 | tutorial/hands on |  |  | |
 | software |  |  | |
 | webpage |  |  | |
 |  |  |  | |
 |  |  |  | |
 |  |  |  | |

## Compare your discussion results 

Compare the list to Table 1 from the [10 simple rules paper](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1007854#sec007).

| Format            | Advantages                                       | Disadvantages                                   |
|-------------------|--------------------------------------------------|-------------------------------------------------|
| PPT and PPTX      | • Easily (re)usable                              | • Limited way to provide detailed training      |
|                   | • Available to multiple OSs/Software             |   instructions                                  |
|                   | • Widespread                                     | • Not version controlled                        |
| Keynote           | • Polished overall aesthetic                     | • Limited to macOS family                       |
|                   |                                                  | • Not version controlled                        |
| PDF               | • Can be displayed identically in any environment| • Not easily editable                           |
|                   |                                                  | • Not version controlled                        |
| TeX               | • Easily editable                                | • Steep learning curve for trainers             |
|                   | • Version controlled                             |                                                 |
| MD, RST, and HTML | • Version controlled                             | • Rendering (need templating to transform into  |
|                   | • Free                                           |   HTML)                                         |
| Google slides    | • Version controlled                              | • Not always possible to use owing to local/    |
|                   | • Free                                           |   institutional policies                        |
|                   |                                                  | • Not always accessible (depending on geographic|
|                   |                                                  |   location)                                     |


## Formats for training material

![](../assets/images/03-formats.png)<!--
style = "width: 100px;"
-->
![](../assests/images/03-overview-formats.png)

![](../assets/images/03-formats.png)<!--
style = "width: 100px;"
-->

![](../assests/images/03-overview-formats.png)

## Summary of training material file ormats

TODO: add one slide with these nice illustration (separate files in the folder) - slide 31 https://docs.google.com/presentation/d/1fVbtwJACMnRM8GgMpGVfi373geFMQCZH6uSoihsRyxM/edit#slide=id.g26da19ef7b0_0_789

## Introduction to interoperability and reproducibility of training material

TODO: create a nice slide

Rule 6 from the 10 simple rules paper is mainly about interoperability [10 simple rules paper](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1007854#sec007).

The key point of Rule 6 is: “Training materials need to be captured in interoperable formats, so that they can be used in different contexts (e.g., operating systems and software) and built upon later. For materials like slides, it is important that other trainers are able to (re)use, fine-tune or even extend them. This means that you should choose a format that supports editing and extension."

## Discuss about the interoperabilty of training material

![](../assets/images/03-activity-team.png)<!--
style = "width: 100px;"
-->
Activity: Have a look at the slides on the [String Database (by Lars Juhl Jensen)](https://www.slideshare.net/larsjuhljensen/the-string-database) on Slideshare. Imagine the slides were downloadable in pptx format. 

1. Could the presentation be extended?
2. Could you choose a few slides and incorporate them in your presentation?
3. Could you easily fix a typo?

## Discuss interoperability and re-usability of training material

![](../assets/images/03-activity-team.png)<!--
style = "width: 100px;"
-->
Activity: Consider the list of in table X. For each format, specify whether it is interoperable, reusable or both and explain the reason for your opinion. 
     
| Formats | Interoperability | Reusability |
| --- | --- | --- |
| pdf | partially | yes | 
| | *A pdf can be read in any OS, but to modify it you need to pay a licence* | *Only as is* | 
| | *Explanation* | *Explanation* | 
| | yes/no/partially | yes/no/partially | 
| | *Explanation* | *Explanation* | 

## TODO: overview slide

          --{{1}}--
1. For a lecture-style presentation, you can annotate each slide with an extensive narrative capturing all aspects of the subject on the slides. You can put the complete transcript of the verbal presentation in the Notes panel in Powerpoint or in Google slides. Suppose you want to share your slides in pdf format. In that case, it is handier to place the detailed content into a handbook or use text-book style reference materials and keep the slides for lectures cleaner, only placing relevant elements directly on the slides. 
2. You may associate “Instructor notes” with the materials, but you don’t need to include them in the materials. The Instructor notes should provide information drawing on your experience or the experience of other instructors. They may consist of technical tips and tricks, common problems, and a description of what parts or exercises are essential and what could be skipped in case of lack of time. Very good examples of Instructor/Trainer notes are provided by the Carpentries ([Carpentry Trainer notes](https://carpentries.github.io/instructor-training/guide/index.html#curriculum), [Instructor notes template](https://carpentries.github.io/lesson-example/guide/index.html)).
3. You may create a lesson plan describing the purpose and the mode of delivery of each piece of material. Lesson plans could contain many practical details, including - for each part of the material - the time needed for the delivery, the learning experiences and expected learning outcomes. Chapter 2.4 shows an example Lesson plan of this lesson.

*****************
TODO: nice illustration with 
- annotation - narrative - check Christof's illustration for FTI Antwerp
- Instructor notes
- lesson plan - reference to content

*****************

## Create and discuss Interoperable and Reproducible training material (text, presentation)

TODO: create slides with guide the practical exercises

Example presentation:
Github: https://github.com/vibbits/material-liascript/blob/master/example-presentation.md?plain=1
Rendering: 
https://liascript.github.io/course/?https://raw.githubusercontent.com/vibbits/material-liascript/master/example-presentation.md#1

To use MarkDown tools to create material (text and presentation)
- LiaScript
  LiaScript
Doc about Liascript
https://liascript.github.io/course/?https://raw.githubusercontent.com/liaScript/docs/master/README.md#1

## Final considerations

TODO: drawing tools which close the circle of interoperability / reusability
https://docs.google.com/presentation/d/1p6xeyCK6GGZ8tq6q6GBxooH4wYiN6U9iVWFBNzqIdWA/edit?usp=sharing
