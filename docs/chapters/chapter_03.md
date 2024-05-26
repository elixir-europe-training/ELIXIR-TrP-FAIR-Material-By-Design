## 2.1 Different types of training material
[@creative_commons_2022]
Reference: https://elixir-europe-training.github.io/ELIXIR-TrP-FAIR-training-handbook/

!!! example "Exercise - google doc to fill in with the group"

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

!!! example "Exercise"

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
| Google slides    | • Version controlled                             | • Not always possible to use owing to local/    |
|                   | • Free                                           |   institutional policies                        |
|                   |                                                  | • Not always accessible (depending on geographic|
|                   |                                                  |   location)                                     |


## 2.2 Discuss interoperability and Reproducibility of training material

!!! example "Exercise"

     Read Rule 6 from the 10 simple rules paper, which is mainly about interoperability [10 simple rules paper](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1007854#sec007).

The key point of Rule 6 is: “Training materials need to be captured in interoperable formats, so that they can be used in different contexts (e.g., operating systems and software) and built upon later. For materials like slides, it is important that other trainers are able to (re)use, fine-tune or even extend them. This means that you should choose a format that supports editing and extension."

!!! example "Exercise - in small groups"

     Have a look at the slides on the [String Database (by Lars Juhl Jensen)](https://www.slideshare.net/larsjuhljensen/the-string-database) on Slideshare. Imagine the slides were downloadable in pptx format. 

     1. Could the presentation be extended?
     2. Could you choose a few slides and incorporate them in your presentation?
     3. Could you easily fix a typo?

!!! example "Exercise - ask to fill in a hackmd document?"

     Consider the list in table 2. For each format, specify whether it is interoperable, reusable or both and explain the reason for your opinion. 
     
     | Formats | Interoperability | Reusability |
     | --- | --- | --- |
     | pdf | partially | yes | 
     | | *A pdf can be read in any OS, but to modify it you need to pay a licence* | *Only as is* | 
     | | *Explanation* | *Explanation* | 
     | | yes/no/partially | yes/no/partially | 
     | | *Explanation* | *Explanation* |  

1. For a lecture-style presentation, you can annotate each slide with an extensive narrative capturing all aspects of the subject on the slides. You can put the complete transcript of the verbal presentation in the Notes panel in Powerpoint or in Google slides. Suppose you want to share your slides in pdf format. In that case, it is handier to place the detailed content into a handbook or use text-book style reference materials and keep the slides for lectures cleaner, only placing relevant elements directly on the slides. 
2. You may associate “Instructor notes” with the materials, but you don’t need to include them in the materials. The Instructor notes should provide information drawing on your experience or the experience of other instructors. They may consist of technical tips and tricks, common problems, and a description of what parts or exercises are essential and what could be skipped in case of lack of time. Very good examples of Instructor/Trainer notes are provided by the Carpentries ([Carpentry Trainer notes](https://carpentries.github.io/instructor-training/guide/index.html#curriculum), [Instructor notes template](https://carpentries.github.io/lesson-example/guide/index.html)).
3. You may create a lesson plan describing the purpose and the mode of delivery of each piece of material. Lesson plans could contain many practical details, including - for each part of the material - the time needed for the delivery, the learning experiences and expected learning outcomes. Chapter 2.4 shows an example Lesson plan of this lesson.

## 2.3 Create and discuss Interoperable and Reproducible training material (text, presentation, video)

Prepare github repo before the course (?) (timing: 10 min)
see ELIXIR lesson template
- Create a Github repo from template
- In case of ELIXIR template setup github pages

drawing tools which close the circle of interoperability / reusability
https://docs.google.com/presentation/d/1p6xeyCK6GGZ8tq6q6GBxooH4wYiN6U9iVWFBNzqIdWA/edit?usp=sharing

To use MarkDown tools to create material (text and presentation)
- LiaScript
  LiaScript
Doc about Liascript
https://liascript.github.io/course/?https://raw.githubusercontent.com/liaScript/docs/master/README.md#1

Example presentation:
Github: https://github.com/vibbits/material-liascript/blob/master/example-presentation.md?plain=1
Rendering: 
https://liascript.github.io/course/?https://raw.githubusercontent.com/vibbits/material-liascript/master/example-presentation.md#1

- QUARTO
see [presentation](https://quarto.org/docs/presentations/revealjs/) on Quarto website and [github](https://github.com/quarto-dev/quarto-web/blob/main/docs/presentations/revealjs/demo/index.qmd)

- mention Video tool for montage - Davinci or Python library moviepy (not sure to recommend it though given the state of the project)

To use Google Slides/Docs (text and presentation)
https://github.com/ssine/pptx2md

## 2.4 Lesson plan

| Teaching Objective | Learning Outcome | Learning Experience | Training Material | Time of Delivery |
|---------------------|------------------|---------------------|-------------------|------------------|
| List different types of training material | Participants will be able to identify and categorize various training materials | Interactive lecture with examples | slides, Google doc | 00:00-00:30 |
| Explain interoperability and reproducibility | Participants will understand the importance of interoperability and reproducibility in training materials | Group discussion and case studies | Case study document, fill in table in hackmd | 00:30-01:00 |
| Create interoperable and reproducible text material | Participants will create their own Markdown-formatted text material | Hands-on activity using Markdown editors | Computers with internet access, Markdown cheat sheets | 01:00-01:30 |
| Create interoperable and reproducible presentation material | Participants will create their own presentations using LiaScript or QUARTO | Hands-on activity with LiaScript and QUARTO tutorials | Computers with internet access, LiaScript and QUARTO guides | 01:30-01:50 |
| Discuss packaging vs base-format | Participants will understand the difference between packaging and base-format in the context of training material | Lecture with Q&A session | PowerPoint slides, FAQ handouts | 01:50-02:00 |


