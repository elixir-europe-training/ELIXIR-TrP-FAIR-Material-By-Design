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
# Let's start with slides from this course provider

[From sequence to structures](https://www.ebi.ac.uk/training/materials/from-sequences-to-structures-materials/uniprot/)

# Our context - we focus on the letters I and R 

![Ten rules for making training materials FAIR](../../../assets/images/10steps_rules4FAIRtraining.png)

# Training materials formats

This presentation will guide you through this session where we will touch on:

- different types of training materials and its re-usability
- different types of training materials and its interoperability
- creating presentations with Liascript, a Markdown dialect or Google slides

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

           --{{0}}--
Welcome, everyone! Today, we’re going to embark on an interactive journey to explore the diverse landscape of training materials in life sciences. Our activity is designed to not only identify the various formats available but also to reflect on our personal preferences and the rationale behind them. Here is the activity Overview: We’ll examine different types of training materials, ranging from slides and videos to datasets and software. For each category, we’ll determine the possible formats they could take. Then, we’ll dive deeper to discuss which formats we predominantly use and, most importantly, why we prefer those over others. This exercise will not only enhance our understanding of the material formats but also provide insights into our teaching methodologies. It’s a chance to share experiences, learn from each other, and possibly discover new ways to engage our audience.
So, let’s get started! Please go to to the joint file. As we proceed, I encourage you to think critically about the ‘why’—it’s the key to understanding our choices and improving our approach to training. Let’s have a productive session!

              {{0-1}}
|  ![](../../../assets/images/04-activities.png)<!-- style = "width: 80px; padding:15px;"-->    |      Activity: How many training materials formats can you list? Identify possible formats for each type of material. Which format(s) do you mostly adopt? Why?   |

              {{1}}
*************

| Material type | Possible format(s) | Format(s) you mostly use | Why? |
| ----------------- | ------------------ | ------------------------ | ---- |
| slides |  PowerPoint/Keynote (.pptx) with speaker notes and animations  • PDF handout (1-up or 3-up with notes)  • Web slides (Reveal.js/Marp/Quarto)  • Cloud deck (Microsoft 365/Google Slides)              |                          |    PPTX for delivery; PDF for distribution. PPTX supports animations/live demos and presenter notes during the course; exporting to PDF gives a stable, portable, non-editable handout students can search and annotate offline  |
| video |        Micro‑lectures (5–8 min MP4)  • Screencasts (live coding/CLI walkthrough)  • Animated explainers (diagram-first)  • Full-session recording with chapters            |                          |     Micro‑lectures reduce cognitive load, fit just‑in‑time review, and are easy to update. Pair with screencasts for tasks (e.g., docking run, queue submission) and keep full recordings as “nice-to-have. |
| dataset  |      Small synthetic CSV/TSV (de‑identified)  • Real subset of HDF5  • Domain-native: FASTA/FASTQ/SDF/PDB/...               |                          | Synthetic CSV/TSV opens everywhere, is light enough for laptops/VMs, avoids privacy/IP issues, and minimizes setup friction. You can add a larger Parquet or domain-native set as an optional “stretch” dataset.     |
| repository | GitHub/GitLab template repo (scaffolded)  • Branch-per-module + solutions branch  • Tagged releases + Zenodo DOI  • Binder/CodeSpaces config |    |  Template repo with tagged releases + DOI makes your course reproducible, citable, and easy to fork. Branching for “solutions” prevents spoilers while enabling instructor diffs. |
| exercises  |   Jupyter notebooks with tests (nbgrader/otter/pytest)  • Short quizzes (H5P/Moodle/Forms)  • Markdown worksheets + expected outputs  • coding exercises  |                          |  Notebook-based exercises with lightweight tests give immediate feedback, support live coding, and store code, outputs, and narrative together—ideal for computational biology workflows    |
| VM/Container |    Docker image (multi‑arch)  • Apptainer/Singularity image for HPC  • Vagrant/VirtualBox VM  • Conda environment  |                          |   Apptainer/Singularity is HPC‑friendly (no root), portable across clusters, and integrates with schedulers. It locks software stacks for reproducible runs.   |
| tutorial/hands-on | Markdown/Sphinx/ReadTheDocs step‑by‑step with copy‑paste blocks  • Quarto/Bookdown site  • Narrative Jupyter notebooks  • Interactive Binder/JupyterHub lab     |                          |    Markdown is diffable, version‑controlled, searchable, and robust offline—great for cluster instructions (modules, job scripts, file paths) where copy‑paste reliability matters.  |
| software |  Conda (Bioconda) package + environment.yml  • Python wheels on PyPI  • Standalone CLI binaries  • Containerized app (Docker/Apptainer)  |                          |  Conda/Bioconda simplifies compiled deps common in life sciences and runs on Linux/macOS/Windows and HPC. Pair with a lock (e.g., conda-lock) and optionally a container for strict reproducibility    |
| webpage |   Static site (Quarto/Jekyll) on GitHub Pages  • LMS page (Moodle/Canvas)  • GitHub Wiki  • ReadTheDocs                 |                          |   tatic site is versioned, searchable, linkable to repo tags, and easy to host for free. It’s fast, works with PRs, and can be snapshotted per course run for stable URLs   |

***********

## Compare your discussion results 

               --{{0}}--
Let's take a moment to reflect on our recent discussions and how they align with the insights from the "10 simple rules" paper. Our conversation has highlighted the various formats we use to disseminate knowledge in life sciences, each with its own set of advantages and challenges.
**PowerPoint (PPT and PPTX)**
- **Advantages:** These formats are easily (re)usable, widely available across different operating systems and software, and have widespread recognition.
- **Disadvantages:** They provide a limited scope for delivering detailed training instructions and lack version control.
**Keynote**
- **Advantages:** Offers a polished overall aesthetic that can enhance the presentation quality.
- **Disadvantages:** Its usage is confined to the macOS family, and it does not support version control.
**PDF**
- **Advantages:** PDFs ensure consistent display across various environments, maintaining the integrity of the content.
- **Disadvantages:** They are not easily editable, which can be a hindrance when updates are needed, and they also lack version control.
**TeX**
- **Advantages:** TeX is easily editable and supports version control, making it a robust choice for collaborative work.
- **Disadvantages:** However, it comes with a steep learning curve that can be a barrier for some trainers.
**Markdown (MD), reStructuredText (RST), and HTML**
- **Advantages:** These formats are version controlled and free, promoting accessibility and ease of updates.
- **Disadvantages:** They require rendering, which may necessitate additional steps to convert into a visually appealing HTML format.
**Google Slides**
- **Advantages:** Google Slides are version controlled and freely available, supporting collaborative efforts.
- **Disadvantages:** Their usage can be restricted by local or institutional policies, and accessibility issues may arise depending on the user's geographic location.
As we continue with our training, let's consider how these formats serve our objectives and the ways in which we can leverage their strengths while mitigating their limitations. Thank you for your thoughtful contributions to this discussion. Now, let's proceed with our next topic.

Compare the list to Table 1 from the '10 simple rules' paper[^1].

| Format            | Advantages                                       | Disadvantages                                   |
|-------------------|--------------------------------------------------|-------------------------------------------------|
| **PPT and PPTX**      | Easily (re)usable                              | Limited way to provide detailed training  instructions    |
|                   | Available to multiple OSs/Software             |                                     |
|                   | Widespread                                     | Not version controlled                        |
| **Keynote**           | Polished overall aesthetic                     | Limited to macOS family                       |
|                   |                                                  | Not version controlled                        |
| **PDF**               | Can be displayed identically in any environment| Not easily editable                           |
|                   |                                                  | Not version controlled                        |
| **TeX**               | Easily editable                                | Steep learning curve for trainers             |
|                   | Version controlled                             |                                                 |
| **MD,RST and HTML** | Version controlled                             | Rendering (need templating to transform into HTML) |
|                   | Free                                           |                                            |
| **Google slides**    | Version controlled                              | Not always possible to use owing to local/institutional policies     |
|                   |    Free                                           |     Not always accessible (depending on geographic location                     |

[^1]: https://journals.plos.org/ploscompbiol/article/figure?id=10.1371/journal.pcbi.1007854.t001


## Summary of training material file formats

               --{{0}}--
Now, we're going to consolidate our understanding of the diverse resources we've been discussing. These resources form the backbone of our life science training and are crucial for a holistic learning experience. Let's take a brief tour through these resources: **Presentations:** Our journey begins with presentations, the visual storytellers of complex concepts. They are the bar charts of our training, providing clear, structured information at a glance. **Website:** The globe of our resources, the website is your go-to destination for a wealth of knowledge, accessible anytime and anywhere, enriching your learning beyond the classroom. **Video:** Like the play button that brings static images to life, our videos offer dynamic and engaging narratives, making complex topics digestible and memorable. **Guidelines:** The checklists of our training, these guidelines are your roadmap to best practices and essential procedures, ensuring you're always on the right track. **Dataset:** Represented by database cylinders, our datasets are the real-world data playgrounds where you can apply and hone your analytical skills. **Tutorial:** The overlapping squares symbolize our tutorials, which provide step-by-step guidance, helping you navigate through practical applications with ease. **Software:** The gear of our toolkit, software training is where you'll gain hands-on experience with the tools that drive life science research forward. Each of these resources is interconnected, creating a comprehensive network that supports your journey in the life sciences. As we move forward, remember that each resource is a piece of a larger puzzle, and together, they form a complete picture of the knowledge and skills you need to succeed.
Now, let's continue to build on this foundation and delve deeper into our next activity. Thank you for your engagement and enthusiasm!

![](../../../assets/images/04-formats.png)<!-- style="width: 700px;" -->

[^1]: https://docs.google.com/presentation/d/1fVbtwJACMnRM8GgMpGVfi373geFMQCZH6uSoihsRyxM/edit#slide=id.g26da19ef7b0_0_789

## Training material crafted for collaboration

               --{{0}}--
Training materials need to be captured in interoperable formats, so that they can be used in different contexts (e.g., operating systems and software) and built upon later. For materials like slides, it is important that other trainers are able to (re)use, fine-tune or even extend them. This means that you should choose a format that supports editing and extension. Interoperability: Ensure your training materials are versatile. Use formats that are compatible across various operating systems and software platforms. Reusability: Design your slides for longevity. Allow other trainers to adopt and adapt your materials with ease. Editability & Extensibility: Select formats that support seamless editing and extension, enabling continuous improvement and customization.

**Enhance your training materials via**

![](../../../assets/images/04-reuse-extend-inter.png)<!-- style="width: 650px;" -->

## How re-usable public training material are

| ![](../../../assets/images/04-activities.png)<!-- style = "width: 80px; padding:15px;"-->  | Activity: Have a look at the slides on the [String Database (by Lars Juhl Jensen)](https://www.slideshare.net/larsjuhljensen/the-string-database) on Slideshare. Imagine the slides were downloadable in pptx format.   |

1. Could the presentation be extended?
2. Could you choose a few slides and incorporate them in your presentation?
3. Could you easily fix a typo?

## Evaluate interoperability and re-usability of training material

| ![](../../../assets/images/04-activities.png)<!-- style = "width: 80px; padding:15px;"-->   | Activity: Consider the list of in table 1. For each format, specify whether it is interoperable, reusable or both and explain the reason for your opinion.   |
     
| Formats | Interoperability | Reusability |
| :---: | :---: | :---: |
| pdf | partially | yes | 
| | *A pdf can be read in any OS, but to modify it you need to pay a licence* | *Only as is* | 
| ... | yes/no/partially | yes/no/partially | 
| | *Explanation* | *Explanation* | 

## The more context you give about your material the better

          --{{0}}--
1. For a lecture-style presentation, you can annotate each slide with an extensive narrative capturing all aspects of the subject on the slides. You can put the complete transcript of the verbal presentation in the Notes panel in Powerpoint or in Google slides. Suppose you want to share your slides in pdf format. In that case, it is handier to place the detailed content into a handbook or use text-book style reference materials and keep the slides for lectures cleaner, only placing relevant elements directly on the slides. 
2. You may associate “Instructor notes” with the materials, but you don’t need to include them in the materials. The Instructor notes should provide information drawing on your experience or the experience of other instructors. They may consist of technical tips and tricks, common problems, and a description of what parts or exercises are essential and what could be skipped in case of lack of time. Very good examples of Instructor/Trainer notes are provided by the Carpentries ([Carpentry Trainer notes](https://carpentries.github.io/instructor-training/guide/index.html#curriculum), [Instructor notes template](https://carpentries.github.io/lesson-example/guide/index.html)).
3. You may create a lesson plan describing the purpose and the mode of delivery of each piece of material. Lesson plans could contain many practical details, including - for each part of the material - the time needed for the delivery, the learning experiences and expected learning outcomes. Chapter 2.4 shows an example Lesson plan of this lesson.

|   |      |      |
| :---------: | :---------: | :---------: |
| ![](../../../assets/images/03-annotation-tutorial.png)<!--
style = "width: 200px;"
-->   |  ![](../../../assets/images/03-bloom-class.png)<!--
style = "width: 200px;"
--> | ![](../../../assets/images/03-bloom-describe.png)<!--
style = "width: 200px;"
--> |
| narratives  | instructor notes     | lesson plan     |

## Instructor notes

About this chapter, you can find the [instructor notes](https://github.com/elixir-europe-training/ELIXIR-TrP-FAIR-Material-By-Design/blob/main/docs/supplementary/trainer-instructions/chapter_04_notes.md) in the GitHub repository.

## Lesson plans

          {{0}}
************************

<svg
   version="1.1"
   id="svg1"
   width="1009.3337"
   height="441.33334"
   viewBox="0 0 1009.3337 441.33334"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:svg="http://www.w3.org/2000/svg">
  <defs
     id="defs1">
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath3">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-176.00001,472.00001)"
         id="path3" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath5">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-427.07203,421.00001)"
         id="path5" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath7">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-427.07203,421.00001)"
         id="path7" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath9">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-427.07203,337.00001)"
         id="path9" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath11">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-427.07203,337.00001)"
         id="path11" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath13">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-423.26301,319.00001)"
         id="path13" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath15">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-423.26301,319.00001)"
         id="path15" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath17">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-423.40602,505.00001)"
         id="path17" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath19">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-423.40602,505.00001)"
         id="path19" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath23">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-692.00002,450.66212)"
         id="path23" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath25">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-692.00002,366.66212)"
         id="path25" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath27">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-260.14,322.88282)"
         id="path27" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath29">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-692.00002,291.66211)"
         id="path29" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath31">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-692.00002,273.66211)"
         id="path31" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath33">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-692.00002,207.66211)"
         id="path33" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath35">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-692.00002,189.66211)"
         id="path35" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath37">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-176.00001,472.00001)"
         id="path37" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath39">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-427.07203,421.00001)"
         id="path39" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath41">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-427.07203,421.00001)"
         id="path41" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath43">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-427.07203,337.00001)"
         id="path43" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath45">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-427.07203,337.00001)"
         id="path45" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath47">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-423.26301,319.00001)"
         id="path47" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath49">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-423.26301,319.00001)"
         id="path49" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath51">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-423.40602,505.00001)"
         id="path51" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath53">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-423.40602,505.00001)"
         id="path53" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath55">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-620.00002,490.00001)"
         id="path55" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath57">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-620.00002,406.00001)"
         id="path57" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath59">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-620.00002,322.00001)"
         id="path59" />
    </clipPath>
    <clipPath
       clipPathUnits="userSpaceOnUse"
       id="clipPath61">
      <path
         d="M 0,0 H 1128 V 708 H 0 Z"
         transform="matrix(1,0,0,-1,-620.00002,238)"
         id="path61" />
    </clipPath>
  </defs>
  <g
     id="g1"
     transform="translate(-56.708335,-92.708337)">
    <path
       id="path2"
       d="M 268.144,181 C 251.51,234.863 201.325,274 142,274 69.098,274 10,214.902 10,142 10,69.098 69.098,10 142,10 c 59.325,0 109.51,39.137 126.144,93 H 255.52 C 239.332,55.871 194.622,22 142,22 75.726,22 22,75.726 22,142 c 0,66.274 53.726,120 120,120 52.622,0 97.332,-33.871 113.52,-81 h 12.624"
       style="fill:#edf4ff;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,44.04167,124.04167)"
       clip-path="url(#clipPath3)" />
    <path
       id="path4"
       d="M 461.079,10 H 178.283 L 71.783,76 H 10 c 0.492,3.944 0.792,7.947 0.892,12 H 448.088 V 71.939 l 29.453,-24.867 v -5.214 h -30.614 v -6.477 c 0,-6.102 1.62,-11.711 4.972,-16.61 2.428,-3.549 5.516,-6.467 9.18,-8.771"
       style="fill:none;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,378.80436,192.04167)"
       clip-path="url(#clipPath5)" />
    <path
       id="path6"
       d="M 454.088,88 V 74.726 l 28.237,-23.841 c 3.353,-2.832 5.876,-5.186 7.571,-7.062 1.694,-1.912 2.836,-3.611 3.426,-5.097 0.626,-1.487 0.939,-3.009 0.939,-4.567 v -0.106 c 0,-1.841 -0.46,-3.451 -1.381,-4.832 -0.885,-1.416 -2.119,-2.513 -3.703,-3.292 -1.584,-0.814 -3.426,-1.221 -5.526,-1.221 -2.394,0 -4.494,0.46 -6.299,1.38 -1.768,0.885 -3.15,2.124 -4.144,3.717 -0.995,1.593 -1.548,3.416 -1.658,5.469 v 0.584 h -18.622 v -0.477 c 0,-4.992 1.308,-9.399 3.923,-13.222 2.616,-3.823 6.226,-6.796 10.831,-8.92 4.641,-2.159 9.946,-3.239 15.914,-3.239 6.079,0 11.383,0.974 15.915,2.92 4.531,1.912 8.049,4.584 10.554,8.018 2.542,3.398 3.813,7.381 3.813,11.947 v 0.106 c 0,3.257 -0.59,6.212 -1.768,8.867 -1.179,2.62 -3.095,5.328 -5.747,8.124 -2.653,2.761 -6.189,5.983 -10.61,9.664 l -16.251,13.327 h 35.426 V 88 h -60.84"
       style="fill:#edf4ff;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,378.80436,192.04167)"
       clip-path="url(#clipPath7)" />
    <path
       id="path8"
       d="m 10.892,10 c -0.1,4.053 -0.4,8.056 -0.892,12 h 61.786 l 106.001,66 h 281.906 c -3.089,-1.946 -5.765,-4.336 -7.963,-7.195 -3.36,-4.372 -5.253,-9.445 -5.729,-15.045 l -0.555,-7.186 h 21.655 V 38.957 h -19.838 l 0.515,-7.179 c 0.43,-5.512 2.172,-10.504 5.345,-14.796 2.026,-2.764 4.496,-5.086 7.355,-6.982 H 10.892"
       style="fill:none;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,378.80436,304.04167)"
       clip-path="url(#clipPath9)" />
    <path
       id="path10"
       d="m 482.797,88 c -5.975,0 -11.198,-0.956 -15.671,-2.87 -4.472,-1.913 -8.018,-4.573 -10.639,-7.982 -2.62,-3.409 -4.122,-7.374 -4.507,-11.896 v -0.678 h 18.291 l 0.105,0.626 c 0.314,2.122 1.555,3.948 3.721,5.478 2.201,1.496 5.101,2.244 8.7,2.244 2.376,0 4.42,-0.383 6.132,-1.148 1.747,-0.765 3.092,-1.809 4.035,-3.13 0.943,-1.357 1.415,-2.905 1.415,-4.644 v -0.104 c 0,-3.061 -1.135,-5.392 -3.406,-6.992 -2.272,-1.6 -5.503,-2.4 -9.696,-2.4 h -8.176 V 41.513 h 8.071 c 2.481,0 4.595,-0.365 6.342,-1.096 1.781,-0.73 3.144,-1.756 4.087,-3.078 0.979,-1.322 1.468,-2.852 1.468,-4.591 v -0.104 c 0,-1.74 -0.419,-3.235 -1.258,-4.488 -0.803,-1.252 -1.991,-2.208 -3.564,-2.869 -1.537,-0.661 -3.389,-0.991 -5.555,-0.991 -2.201,0 -4.14,0.347 -5.818,1.043 -1.642,0.661 -2.952,1.617 -3.93,2.87 -0.944,1.217 -1.52,2.643 -1.73,4.278 v 0.47 H 453.71 v -0.731 c 0.401,-4.487 1.799,-8.382 4.245,-11.687 2.446,-3.339 5.765,-5.93 9.958,-7.774 4.227,-1.843 9.154,-2.765 14.779,-2.765 5.73,0 10.709,0.835 14.936,2.504 4.263,1.635 7.547,3.948 9.853,6.94 2.306,2.991 3.459,6.504 3.459,10.539 v 0.104 c 0,3.165 -0.716,5.93 -2.148,8.296 -1.398,2.33 -3.285,4.243 -5.661,5.739 -2.375,1.495 -4.978,2.539 -7.808,3.13 v 0.365 c 5.66,0.557 10.167,2.348 13.521,5.374 3.389,3.026 5.084,7.026 5.084,12 v 0.105 c 0,4.626 -1.276,8.661 -3.826,12.104 -2.551,3.409 -6.149,6.07 -10.796,7.983 C 494.659,87.061 489.156,88 482.797,88"
       style="fill:#edf4ff;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,378.80436,304.04167)"
       clip-path="url(#clipPath11)" />
    <path
       id="path12"
       d="M 476.31,76 H 179.882 L 73.881,10 H 12.907 C 12.157,14.248 11.184,18.419 10,22.5 h 60.12 l 112.002,131.002 304.016,0.477 v -7.276 h -38.401 v -23.819 l 0.85,-1.422 c 1.953,-3.266 3.923,-6.513 5.912,-9.743 2.012,-3.245 3.996,-6.475 5.962,-9.704 l 5.925,-9.73 c 1.977,-3.247 3.955,-6.477 5.932,-9.688 1.339,-2.199 2.67,-4.398 3.992,-6.597"
       style="fill:none;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,373.72567,328.04167)"
       clip-path="url(#clipPath13)" />
    <path
       id="path14"
       d="m 459.608,114.865 c -1.975,3.207 -3.932,6.432 -5.871,9.675 v 16.163 h 38.401 V 154 h 18.743 v -13.297 h 7.856 v -15.46 h -7.856 V 76 h -27.575 c -1.939,3.243 -3.896,6.487 -5.871,9.73 -1.975,3.207 -3.95,6.432 -5.924,9.675 l -5.925,9.73 c -1.975,3.243 -3.967,6.487 -5.978,9.73 m 10.664,11.081 h 22.405 v -36.27 h -0.431 l -4.417,7.135 c -1.436,2.378 -2.89,4.757 -4.362,7.135 -1.436,2.378 -2.909,4.775 -4.417,7.189 l -4.416,7.135 c -1.436,2.379 -2.89,4.757 -4.362,7.136 v 0.54"
       style="fill:#edf4ff;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,373.72567,328.04167)"
       clip-path="url(#clipPath15)" />
    <path
       id="path16"
       d="M 476.577,10 H 183.968 l -114,132 H 10 c 1.119,3.922 2.044,7.925 2.763,12 h 60.978 l 106.5,-66 H 481.173 V 38.507 l -19.58,13.316 V 20.369 L 476.577,10"
       style="fill:none;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,373.91635,80.04167)"
       clip-path="url(#clipPath17)" />
    <path
       id="path18"
       d="M 487.174,88 V 27.459 h -0.426 L 467.594,40.486 V 23.514 L 487.12,10 h 19.474 v 78 h -19.42"
       style="fill:#edf4ff;fill-opacity:1;fill-rule:evenodd;stroke:none"
       transform="matrix(1.3333333,0,0,1.3333333,373.91635,80.04167)"
       clip-path="url(#clipPath19)" />
    <path
       id="path22"
       d="M 8.6025391,-9.5039056 H 5.1806641 V 6.2500004e-7 H 3.7861328 V -9.5039056 H 0.36425781 V -10.664062 H 8.6025391 Z M 11.435547,6.2500004e-7 H 10.087891 V -7.9218744 h 1.347656 z M 9.9707031,-10.031249 c 0,-0.216797 0.064453,-0.401368 0.1992189,-0.550782 0.140625,-0.155273 0.339844,-0.234375 0.597656,-0.234375 0.263672,0 0.462891,0.0791 0.597656,0.234375 0.140625,0.149414 0.210938,0.333985 0.210938,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210938,0.5507809 -0.134765,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257812,0 -0.457031,-0.073242 -0.597656,-0.2226562 -0.134766,-0.1464844 -0.1992189,-0.3310547 -0.1992189,-0.5507809 z m 4.8955079,2.1093746 0.03516,0.8789063 c 0.585938,-0.6855469 1.371094,-1.03125 2.355469,-1.03125 1.107422,0 1.863281,0.4277344 2.261719,1.2773437 0.263672,-0.3808593 0.609375,-0.6914062 1.03125,-0.9257812 0.421875,-0.234375 0.919922,-0.3515625 1.5,-0.3515625 1.734375,0 2.616211,0.9228515 2.648437,2.765625 V 6.2500004e-7 H 23.338867 V -5.2265619 c 0,-0.5683593 -0.128906,-0.9960937 -0.386719,-1.2773437 -0.257812,-0.28125 -0.691406,-0.421875 -1.300781,-0.421875 -0.500976,0 -0.919922,0.1523437 -1.253906,0.4570312 -0.328125,0.2988282 -0.521484,0.7001953 -0.574219,1.2070313 V 6.2500004e-7 H 18.463867 V -5.1914056 c 0,-1.1542969 -0.568359,-1.734375 -1.699219,-1.734375 -0.890625,0 -1.49707,0.3808594 -1.816406,1.1367187 V 6.2500004e-7 H 13.588867 V -7.9218744 Z m 15.155273,8.07421878 c -1.072265,0 -1.945312,-0.3515625 -2.625,-1.0546875 C 26.722656,-1.6113275 26.388672,-2.5576166 26.388672,-3.7382806 v -0.2578125 c 0,-0.7792969 0.146484,-1.4794922 0.445312,-2.0976563 0.304688,-0.6152343 0.726563,-1.1015625 1.265625,-1.453125 0.539063,-0.3515625 1.125,-0.5273437 1.757813,-0.5273437 1.03125,0 1.831055,0.3398437 2.402344,1.0195312 0.568359,0.6796875 0.855468,1.6523438 0.855468,2.9179688 v 0.5625 h -5.367187 c 0.01465,0.7822265 0.240234,1.415039 0.679687,1.8984375 0.436524,0.477539 0.990235,0.71484373 1.664063,0.71484373 0.483398,0 0.890625,-0.0966797 1.21875,-0.29296873 0.333984,-0.1933594 0.626953,-0.4511719 0.878906,-0.7734375 l 0.820313,0.6445312 c -0.665039,1.02539065 -1.661133,1.53515628 -2.988282,1.53515628 z M 29.857422,-6.9609369 c -0.547852,0 -1.007813,0.1992188 -1.382813,0.5976563 -0.36914,0.3984375 -0.594726,0.9580078 -0.679687,1.6757812 h 3.960937 v -0.1054687 c -0.04102,-0.6855469 -0.228515,-1.21875 -0.5625,-1.59375 -0.328125,-0.3808594 -0.773437,-0.5742188 -1.335937,-0.5742188 z M 38.59082,6.2500004e-7 V -10.664062 h 3.011719 c 0.919922,0 1.737305,0.208008 2.449219,0.621094 0.717773,0.4072264 1.268554,0.9902343 1.652344,1.7460936 0.389648,0.7587891 0.588867,1.6259766 0.597656,2.6015625 v 0.6796875 c 0,1.0078125 -0.196289,1.8925782 -0.585938,2.6484375 -0.392578,0.7587891 -0.946289,1.3417969 -1.664062,1.74609378 C 43.331055,-0.21386656 42.496094,-0.00585875 41.543945,6.2500004e-7 Z M 39.99707,-9.5039056 v 8.3554687 h 1.476563 c 1.083984,0 1.927734,-0.3339843 2.53125,-1.0078125 0.600586,-0.6796875 0.902344,-1.640625 0.902344,-2.8828125 v -0.6210937 c 0,-1.209961 -0.28711,-2.1503906 -0.855469,-2.8242188 -0.571289,-0.6708984 -1.376953,-1.0107422 -2.414063,-1.0195312 z M 49.670898,6.2500004e-7 H 48.323242 V -7.9218744 h 1.347656 z M 48.206055,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199218,-0.550782 0.140625,-0.155273 0.339844,-0.234375 0.597657,-0.234375 0.263672,0 0.46289,0.0791 0.597656,0.234375 0.140625,0.149414 0.210937,0.333985 0.210937,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210937,0.5507809 -0.134766,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257813,0 -0.457032,-0.073242 -0.597657,-0.2226562 -0.134765,-0.1464844 -0.199218,-0.3310547 -0.199218,-0.5507809 z m 8.235351,7.9335934 c 0,-0.366211 -0.137695,-0.6503906 -0.410156,-0.8554688 -0.275391,-0.2021484 -0.755859,-0.3779297 -1.441406,-0.5273437 -0.688477,-0.1464844 -1.236328,-0.3222656 -1.640625,-0.5273438 -0.398438,-0.2021484 -0.697266,-0.4453125 -0.890625,-0.7265625 -0.1875,-0.2871093 -0.28125,-0.6269531 -0.28125,-1.0195312 0,-0.647461 0.272461,-1.1953125 0.820312,-1.640625 0.544922,-0.4511719 1.248047,-0.6796875 2.109375,-0.6796875 0.896485,0 1.623047,0.234375 2.179688,0.703125 0.5625,0.4628906 0.84375,1.0517578 0.84375,1.7695312 h -1.371094 c 0,-0.3662109 -0.158203,-0.6826172 -0.46875,-0.9492187 -0.313477,-0.272461 -0.708984,-0.4101563 -1.183594,-0.4101563 -0.500976,0 -0.890625,0.1113282 -1.171875,0.328125 -0.27539,0.2109375 -0.410156,0.4921875 -0.410156,0.84375 0,0.3222657 0.128906,0.5683594 0.386719,0.7382813 0.257812,0.1640625 0.726562,0.3251953 1.40625,0.4804687 0.679687,0.1494141 1.224609,0.328125 1.640625,0.5390625 0.421875,0.2050782 0.732422,0.4541016 0.9375,0.75 0.202148,0.2988282 0.304687,0.65625 0.304687,1.078125 0,0.7119141 -0.287109,1.28320315 -0.855469,1.71093753 -0.5625,0.43066406 -1.297851,0.64453125 -2.203125,0.64453125 -0.632812,0 -1.195312,-0.11425782 -1.6875,-0.33984375 -0.486328,-0.22558594 -0.867187,-0.5390625 -1.148437,-0.93750003 -0.275391,-0.4042968 -0.410156,-0.84375 -0.410156,-1.3125 h 1.359375 c 0.02344,0.4541016 0.202148,0.8144532 0.539062,1.078125 0.342774,0.2666016 0.791016,0.39843753 1.347656,0.39843753 0.515625,0 0.925782,-0.0996093 1.230469,-0.30468753 0.310547,-0.2109375 0.46875,-0.4863281 0.46875,-0.8320312 z m 4.948242,-7.7460938 v 1.921875 h 1.488282 v 1.0429688 h -1.488282 v 4.9101562 c 0,0.3222657 0.06445,0.5625 0.199219,0.7265625 0.131836,0.1582032 0.357422,0.234375 0.679688,0.234375 0.155273,0 0.36914,-0.029297 0.644531,-0.09375 V 6.2500004e-7 C 62.552734,0.09961 62.204102,0.15234438 61.870117,0.15234438 c -0.603515,0 -1.060547,-0.18164063 -1.371094,-0.55078125 -0.304687,-0.36621094 -0.457031,-0.89062503 -0.457031,-1.57031253 v -4.9101562 h -1.441406 v -1.0429688 h 1.441406 v -1.921875 z m 6.881836,3.1289063 c -0.205078,-0.029297 -0.421875,-0.046875 -0.65625,-0.046875 -0.890625,0 -1.49707,0.3808594 -1.816406,1.1367187 V 6.2500004e-7 H 64.451172 V -7.9218744 h 1.3125 l 0.02344,0.9140625 c 0.445313,-0.7089843 1.072266,-1.0664062 1.886719,-1.0664062 0.263672,0 0.462891,0.035156 0.597656,0.1054687 z M 70.987305,6.2500004e-7 H 69.639648 V -7.9218744 h 1.347657 z M 69.522461,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199219,-0.550782 0.140625,-0.155273 0.339843,-0.234375 0.597656,-0.234375 0.263672,0 0.462891,0.0791 0.597656,0.234375 0.140625,0.149414 0.210938,0.333985 0.210938,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210938,0.5507809 -0.134765,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257813,0 -0.457031,-0.073242 -0.597656,-0.2226562 -0.134766,-0.1464844 -0.199219,-0.3310547 -0.199219,-0.5507809 z m 10.333008,6.1523434 c 0,1.2128906 -0.278321,2.1884765 -0.832032,2.92968748 -0.55664,0.73535156 -1.300781,1.1015625 -2.238281,1.1015625 -1.007812,0 -1.787109,-0.35449219 -2.332031,-1.06640625 L 74.394531,6.2500004e-7 H 73.152344 V -11.249999 H 74.5 v 4.1953121 c 0.544922,-0.6796875 1.300781,-1.0195312 2.261719,-1.0195312 0.960937,0 1.713867,0.3632812 2.261718,1.0898437 0.553711,0.7265625 0.832032,1.7226563 0.832032,2.9882813 z m -1.359375,-0.1523438 c 0,-0.9199218 -0.181641,-1.6318359 -0.539063,-2.1328125 -0.351562,-0.5068359 -0.861328,-0.7617187 -1.523437,-0.7617187 -0.899414,0 -1.543946,0.4189453 -1.933594,1.2539062 v 3.421875 c 0.413086,0.8291016 1.060547,1.2421875 1.945312,1.2421875 0.647461,0 1.151368,-0.2490234 1.511719,-0.75 0.357422,-0.4980468 0.539063,-1.2568359 0.539063,-2.2734375 z m 7.957031,3.24609378 c -0.524414,0.62695312 -1.297852,0.9375 -2.320313,0.9375 -0.84375,0 -1.488281,-0.24609375 -1.933593,-0.73828125 C 81.759766,-1.0781244 81.537109,-1.8046869 81.53125,-2.7656244 v -5.15625 h 1.359375 v 5.1210938 c 0,1.1953125 0.486328,1.7929687 1.464844,1.7929687 1.03125,0 1.716797,-0.3808593 2.0625,-1.1484375 v -5.765625 h 1.359375 V 6.2500004e-7 H 86.488281 Z M 91.65918,-9.8437494 v 1.921875 h 1.488281 v 1.0429688 H 91.65918 v 4.9101562 c 0,0.3222657 0.06445,0.5625 0.199218,0.7265625 0.131836,0.1582032 0.357422,0.234375 0.679688,0.234375 0.155273,0 0.369141,-0.029297 0.644531,-0.09375 V 6.2500004e-7 C 92.822266,0.09961 92.473633,0.15234438 92.139648,0.15234438 c -0.603515,0 -1.060546,-0.18164063 -1.371093,-0.55078125 -0.304688,-0.36621094 -0.457032,-0.89062503 -0.457032,-1.57031253 v -4.9101562 h -1.441406 v -1.0429688 h 1.441406 v -1.921875 z M 96.185547,6.2500004e-7 H 94.837891 V -7.9218744 h 1.347656 z M 94.720703,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199219,-0.550782 0.140625,-0.155273 0.339844,-0.234375 0.597656,-0.234375 0.263672,0 0.462891,0.0791 0.597656,0.234375 0.140625,0.149414 0.210938,0.333985 0.210938,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210938,0.5507809 -0.134765,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257812,0 -0.457031,-0.073242 -0.597656,-0.2226562 -0.134766,-0.1464844 -0.199219,-0.3310547 -0.199219,-0.5507809 z m 3.266602,5.9999996 c 0,-0.7792968 0.152343,-1.4794922 0.457031,-2.0976562 0.304687,-0.6240235 0.726562,-1.1044922 1.265625,-1.4414063 0.544919,-0.3339843 1.171879,-0.5039062 1.874999,-0.5039062 1.07813,0 1.94824,0.375 2.61328,1.125 0.6709,0.7441406 1.00781,1.734375 1.00781,2.9765625 v 0.09375 c 0,0.7734375 -0.14941,1.4707031 -0.44531,2.0859375 -0.29883,0.609375 -0.72363,1.08691404 -1.27734,1.42968748 -0.54785,0.34570312 -1.17774,0.515625 -1.88672,0.515625 -1.07227,0 -1.942383,-0.375 -2.613282,-1.125 C 98.318359,-1.7226556 97.987305,-2.7099603 97.987305,-3.9374994 Z m 1.359375,0.1523438 c 0,0.8847656 0.202148,1.5908203 0.609375,2.1210937 0.413085,0.5332032 0.960935,0.79687503 1.640625,0.79687503 0.68555,0 1.2334,-0.26953123 1.64062,-0.80859373 0.4043,-0.5390625 0.60938,-1.2919922 0.60938,-2.2617188 0,-0.8730468 -0.20801,-1.5820312 -0.62109,-2.1210937 -0.41602,-0.5390625 -0.96094,-0.8085938 -1.64063,-0.8085938 -0.67383,0 -1.21582,0.2666016 -1.628905,0.796875 -0.407227,0.5332032 -0.609375,1.2949219 -0.609375,2.2851563 z m 8.83301,-4.0429688 0.0469,0.9960938 c 0.60059,-0.7646485 1.38867,-1.1484375 2.36719,-1.1484375 1.67871,0 2.52246,0.946289 2.53125,2.8359375 V 6.2500004e-7 h -1.34766 V -5.2499994 c -0.009,-0.5683593 -0.14062,-0.9902343 -0.39843,-1.265625 -0.25196,-0.2724609 -0.65039,-0.4101562 -1.19532,-0.4101562 -0.43945,0 -0.82617,0.1171875 -1.16015,0.3515625 -0.32813,0.234375 -0.58594,0.5449219 -0.77344,0.9257812 V 6.2500004e-7 h -1.34766 V -7.9218744 Z m 0,0"
       style="fill:#484848;fill-opacity:1;fill-rule:nonzero;stroke:none"
       aria-label="Time Distribution"
       transform="matrix(1.3333333,0,0,1.3333333,732.04167,152.49219)"
       clip-path="url(#clipPath23)" />
    <path
       id="path24"
       d="m 9.0830078,-3.3867181 c -0.1347656,1.133789 -0.5507812,2.0097656 -1.2539062,2.62499998 -0.6972657,0.609375 -1.6259766,0.9140625 -2.7890625,0.9140625 -1.2597657,0 -2.2705078,-0.45117188 -3.0351563,-1.35937498 C 1.2460937,-2.1123041 0.86816406,-3.322265 0.86816406,-4.8398431 v -1.0195313 c 0,-0.9902343 0.17578124,-1.8632812 0.52734374,-2.6132812 0.3574219,-0.75 0.8613281,-1.3271485 1.5117188,-1.7343754 0.6474609,-0.404296 1.4003906,-0.609375 2.2617187,-0.609375 1.1308594,0 2.0390625,0.316407 2.71875,0.9492191 0.6855469,0.6328125 1.0839844,1.5087891 1.1953125,2.625 H 7.6650391 C 7.5478516,-8.0859369 7.28125,-8.6982416 6.8681641,-9.0820306 6.4609375,-9.46289 5.8955078,-9.6562494 5.1689453,-9.6562494 c -0.8994141,0 -1.6054687,0.3339844 -2.1210937,0.9960938 -0.5097657,0.665039 -0.7617188,1.6113281 -0.7617188,2.8359375 v 1.03125 c 0,1.1572265 0.2402344,2.0800781 0.7265625,2.765625 0.4833985,0.6796875 1.1601563,1.0195312 2.0273438,1.0195312 0.7792968,0 1.3769531,-0.1757812 1.7929687,-0.5273437 0.421875,-0.3515625 0.6972656,-0.9667969 0.8320313,-1.8515625 z m 1.3359372,-0.6445313 c 0,-0.7792968 0.152344,-1.4794922 0.457032,-2.0976562 0.304687,-0.6240235 0.726562,-1.1044922 1.265625,-1.4414063 0.544921,-0.3339843 1.171875,-0.5039062 1.875,-0.5039062 1.078125,0 1.948242,0.375 2.613281,1.125 0.670898,0.7441406 1.007812,1.734375 1.007812,2.9765625 v 0.09375 c 0,0.7734375 -0.149414,1.4707031 -0.445312,2.0859375 -0.298828,0.609375 -0.723633,1.08691404 -1.277344,1.42968748 -0.547851,0.34570312 -1.177734,0.515625 -1.886719,0.515625 -1.072265,0 -1.942382,-0.375 -2.613281,-1.125 C 10.75,-1.7226556 10.418945,-2.7099603 10.418945,-3.9374994 Z m 1.359375,0.1523438 c 0,0.8847656 0.202149,1.5908203 0.609375,2.1210937 0.413086,0.5332032 0.960938,0.79687503 1.640625,0.79687503 0.685547,0 1.233399,-0.26953123 1.640625,-0.80859373 0.404297,-0.5390625 0.609375,-1.2919922 0.609375,-2.2617188 0,-0.8730468 -0.208008,-1.5820312 -0.621093,-2.1210937 -0.416016,-0.5390625 -0.960938,-0.8085938 -1.640625,-0.8085938 -0.673829,0 -1.215821,0.2666016 -1.628907,0.796875 -0.407226,0.5332032 -0.609375,1.2949219 -0.609375,2.2851563 z m 8.830078,-4.0429688 0.04687,0.9960938 c 0.600586,-0.7646485 1.388672,-1.1484375 2.367188,-1.1484375 1.678711,0 2.522461,0.946289 2.53125,2.8359375 V 6.2500004e-7 H 24.206055 V -5.2499994 c -0.0088,-0.5683593 -0.140625,-0.9902343 -0.398438,-1.265625 -0.251953,-0.2724609 -0.65039,-0.4101562 -1.195312,-0.4101562 -0.439453,0 -0.826172,0.1171875 -1.160157,0.3515625 -0.328125,0.234375 -0.585937,0.5449219 -0.773437,0.9257812 V 6.2500004e-7 H 19.331055 V -7.9218744 Z m 8.81543,-1.921875 v 1.921875 h 1.488281 v 1.0429688 h -1.488281 v 4.9101562 c 0,0.3222657 0.06445,0.5625 0.199219,0.7265625 0.131836,0.1582032 0.357422,0.234375 0.679687,0.234375 0.155274,0 0.369141,-0.029297 0.644532,-0.09375 V 6.2500004e-7 C 30.586914,0.09961 30.238281,0.15234438 29.904297,0.15234438 c -0.603516,0 -1.060547,-0.18164063 -1.371094,-0.55078125 -0.304687,-0.36621094 -0.457031,-0.89062503 -0.457031,-1.57031253 v -4.9101562 h -1.441406 v -1.0429688 h 1.441406 v -1.921875 z m 6.342774,9.99609378 c -1.072266,0 -1.945313,-0.3515625 -2.625,-1.0546875 C 32.467773,-1.6113275 32.133789,-2.5576166 32.133789,-3.7382806 v -0.2578125 c 0,-0.7792969 0.146484,-1.4794922 0.445313,-2.0976563 0.304687,-0.6152343 0.726562,-1.1015625 1.265625,-1.453125 0.539062,-0.3515625 1.125,-0.5273437 1.757812,-0.5273437 1.03125,0 1.831055,0.3398437 2.402344,1.0195312 0.568359,0.6796875 0.855469,1.6523438 0.855469,2.9179688 v 0.5625 h -5.367188 c 0.01465,0.7822265 0.240234,1.415039 0.679688,1.8984375 0.436523,0.477539 0.990234,0.71484373 1.664062,0.71484373 0.483398,0 0.890625,-0.0966797 1.21875,-0.29296873 0.333984,-0.1933594 0.626953,-0.4511719 0.878906,-0.7734375 l 0.820313,0.6445312 C 38.089844,-0.35742125 37.09375,0.15234438 35.766602,0.15234438 Z M 35.602539,-6.9609369 c -0.547852,0 -1.007812,0.1992188 -1.382812,0.5976563 -0.369141,0.3984375 -0.594727,0.9580078 -0.679688,1.6757812 h 3.960938 v -0.1054687 c -0.04102,-0.6855469 -0.228516,-1.21875 -0.5625,-1.59375 -0.328125,-0.3808594 -0.773438,-0.5742188 -1.335938,-0.5742188 z m 6.09668,-0.9609375 0.04687,0.9960938 c 0.600586,-0.7646485 1.388672,-1.1484375 2.367187,-1.1484375 1.678711,0 2.522461,0.946289 2.53125,2.8359375 V 6.2500004e-7 H 45.296875 V -5.2499994 c -0.0088,-0.5683593 -0.140625,-0.9902343 -0.398438,-1.265625 -0.251953,-0.2724609 -0.65039,-0.4101562 -1.195312,-0.4101562 -0.439453,0 -0.826172,0.1171875 -1.160156,0.3515625 -0.328125,0.234375 -0.585938,0.5449219 -0.773438,0.9257812 V 6.2500004e-7 H 40.421875 V -7.9218744 Z m 8.815429,-1.921875 v 1.921875 h 1.488282 v 1.0429688 h -1.488282 v 4.9101562 c 0,0.3222657 0.06445,0.5625 0.199219,0.7265625 0.131836,0.1582032 0.357422,0.234375 0.679688,0.234375 0.155273,0 0.36914,-0.029297 0.644531,-0.09375 V 6.2500004e-7 C 51.677734,0.09961 51.329102,0.15234438 50.995117,0.15234438 c -0.603515,0 -1.060547,-0.18164063 -1.371094,-0.55078125 -0.304687,-0.36621094 -0.457031,-0.89062503 -0.457031,-1.57031253 v -4.9101562 h -1.441406 v -1.0429688 h 1.441406 v -1.921875 z M 57.493164,6.2500004e-7 V -10.664062 h 3.011719 c 0.919922,0 1.737304,0.208008 2.449219,0.621094 0.717773,0.4072264 1.268554,0.9902343 1.652343,1.7460936 0.389649,0.7587891 0.588867,1.6259766 0.597657,2.6015625 v 0.6796875 c 0,1.0078125 -0.19629,1.8925782 -0.585938,2.6484375 -0.392578,0.7587891 -0.946289,1.3417969 -1.664062,1.74609378 C 62.233398,-0.21386656 61.398437,-0.00585875 60.446289,6.2500004e-7 Z M 58.899414,-9.5039056 v 8.3554687 h 1.476563 c 1.083984,0 1.927734,-0.3339843 2.53125,-1.0078125 0.600585,-0.6796875 0.902343,-1.640625 0.902343,-2.8828125 v -0.6210937 c 0,-1.209961 -0.287109,-2.1503906 -0.855468,-2.8242188 -0.57129,-0.6708984 -1.376954,-1.0107422 -2.414063,-1.0195312 z M 68.570312,6.2500004e-7 H 67.222656 V -7.9218744 h 1.347656 z M 67.105469,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199218,-0.550782 0.140625,-0.155273 0.339844,-0.234375 0.597657,-0.234375 0.263672,0 0.46289,0.0791 0.597656,0.234375 0.140625,0.149414 0.210937,0.333985 0.210937,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210937,0.5507809 -0.134766,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257813,0 -0.457032,-0.073242 -0.597657,-0.2226562 -0.134765,-0.1464844 -0.199218,-0.3310547 -0.199218,-0.5507809 z m 4.895508,2.1093746 0.03516,0.8789063 c 0.585937,-0.6855469 1.371094,-1.03125 2.355469,-1.03125 1.107421,0 1.863281,0.4277344 2.261718,1.2773437 0.263672,-0.3808593 0.609375,-0.6914062 1.03125,-0.9257812 0.421875,-0.234375 0.919922,-0.3515625 1.5,-0.3515625 1.734375,0 2.616211,0.9228515 2.648438,2.765625 V 6.2500004e-7 H 80.473633 V -5.2265619 c 0,-0.5683593 -0.128906,-0.9960937 -0.386719,-1.2773437 -0.257812,-0.28125 -0.691406,-0.421875 -1.300781,-0.421875 -0.500977,0 -0.919922,0.1523437 -1.253906,0.4570312 -0.328125,0.2988282 -0.521485,0.7001953 -0.574219,1.2070313 V 6.2500004e-7 H 75.598633 V -5.1914056 c 0,-1.1542969 -0.56836,-1.734375 -1.699219,-1.734375 -0.890625,0 -1.49707,0.3808594 -1.816406,1.1367187 V 6.2500004e-7 H 70.723633 V -7.9218744 Z M 87.15625,0.15234438 c -1.072266,0 -1.945313,-0.3515625 -2.625,-1.0546875 C 83.857422,-1.6113275 83.523437,-2.5576166 83.523437,-3.7382806 v -0.2578125 c 0,-0.7792969 0.146485,-1.4794922 0.445313,-2.0976563 0.304687,-0.6152343 0.726562,-1.1015625 1.265625,-1.453125 0.539062,-0.3515625 1.125,-0.5273437 1.757812,-0.5273437 1.03125,0 1.831055,0.3398437 2.402344,1.0195312 0.56836,0.6796875 0.855469,1.6523438 0.855469,2.9179688 v 0.5625 h -5.367188 c 0.01465,0.7822265 0.240235,1.415039 0.679688,1.8984375 0.436523,0.477539 0.990234,0.71484373 1.664062,0.71484373 0.483399,0 0.890625,-0.0966797 1.21875,-0.29296873 0.333985,-0.1933594 0.626954,-0.4511719 0.878907,-0.7734375 l 0.820312,0.6445312 C 89.479492,-0.35742125 88.483398,0.15234438 87.15625,0.15234438 Z M 86.992187,-6.9609369 c -0.547851,0 -1.007812,0.1992188 -1.382812,0.5976563 -0.369141,0.3984375 -0.594727,0.9580078 -0.679688,1.6757812 h 3.960938 v -0.1054687 c -0.04102,-0.6855469 -0.228516,-1.21875 -0.5625,-1.59375 C 88,-6.7675775 87.554687,-6.9609369 86.992187,-6.9609369 Z m 6.09668,-0.9609375 0.04687,0.9960938 c 0.600586,-0.7646485 1.388672,-1.1484375 2.367188,-1.1484375 1.678711,0 2.522461,0.946289 2.53125,2.8359375 V 6.2500004e-7 H 96.686523 V -5.2499994 c -0.0088,-0.5683593 -0.140625,-0.9902343 -0.398437,-1.265625 -0.251953,-0.2724609 -0.650391,-0.4101562 -1.195313,-0.4101562 -0.439453,0 -0.826171,0.1171875 -1.160156,0.3515625 -0.328125,0.234375 -0.585937,0.5449219 -0.773437,0.9257812 V 6.2500004e-7 H 91.811523 V -7.9218744 Z m 11.592773,5.8242188 c 0,-0.366211 -0.13769,-0.6503906 -0.41016,-0.8554688 -0.27539,-0.2021484 -0.75585,-0.3779297 -1.4414,-0.5273437 -0.68848,-0.1464844 -1.23633,-0.3222656 -1.64063,-0.5273438 -0.39843,-0.2021484 -0.69726,-0.4453125 -0.89062,-0.7265625 -0.1875,-0.2871093 -0.28125,-0.6269531 -0.28125,-1.0195312 0,-0.647461 0.27246,-1.1953125 0.82031,-1.640625 0.54492,-0.4511719 1.24805,-0.6796875 2.10938,-0.6796875 0.89648,0 1.62304,0.234375 2.17968,0.703125 0.5625,0.4628906 0.84375,1.0517578 0.84375,1.7695312 h -1.37109 c 0,-0.3662109 -0.1582,-0.6826172 -0.46875,-0.9492187 -0.31348,-0.272461 -0.70898,-0.4101563 -1.18359,-0.4101563 -0.50098,0 -0.89063,0.1113282 -1.17188,0.328125 -0.27539,0.2109375 -0.41016,0.4921875 -0.41016,0.84375 0,0.3222657 0.12891,0.5683594 0.38672,0.7382813 0.25782,0.1640625 0.72657,0.3251953 1.40625,0.4804687 0.67969,0.1494141 1.22461,0.328125 1.64063,0.5390625 0.42187,0.2050782 0.73242,0.4541016 0.9375,0.75 0.20215,0.2988282 0.30469,0.65625 0.30469,1.078125 0,0.7119141 -0.28711,1.28320315 -0.85547,1.71093753 -0.5625,0.43066406 -1.29785,0.64453125 -2.20313,0.64453125 -0.63281,0 -1.19531,-0.11425782 -1.6875,-0.33984375 -0.48633,-0.22558594 -0.86719,-0.5390625 -1.14844,-0.93750003 -0.275386,-0.4042968 -0.410152,-0.84375 -0.410152,-1.3125 h 1.359372 c 0.0234,0.4541016 0.20215,0.8144532 0.53907,1.078125 0.34277,0.2666016 0.79101,0.39843753 1.34765,0.39843753 0.51563,0 0.92578,-0.0996093 1.23047,-0.30468753 0.31055,-0.2109375 0.46875,-0.4863281 0.46875,-0.8320312 z M 109.2666,6.2500004e-7 h -1.34765 V -7.9218744 h 1.34765 z M 107.80176,-10.031249 c 0,-0.216797 0.0644,-0.401368 0.19922,-0.550782 0.14062,-0.155273 0.33984,-0.234375 0.59765,-0.234375 0.26367,0 0.46289,0.0791 0.59766,0.234375 0.14062,0.149414 0.21094,0.333985 0.21094,0.550782 0,0.2197262 -0.0703,0.4042965 -0.21094,0.5507809 -0.13477,0.149414 -0.33399,0.2226562 -0.59766,0.2226562 -0.25781,0 -0.45703,-0.073242 -0.59765,-0.2226562 -0.13477,-0.1464844 -0.19922,-0.3310547 -0.19922,-0.5507809 z m 3.2666,5.9999996 c 0,-0.7792968 0.15234,-1.4794922 0.45703,-2.0976562 0.30469,-0.6240235 0.72656,-1.1044922 1.26563,-1.4414063 0.54492,-0.3339843 1.17187,-0.5039062 1.875,-0.5039062 1.07812,0 1.94824,0.375 2.61328,1.125 0.6709,0.7441406 1.00781,1.734375 1.00781,2.9765625 v 0.09375 c 0,0.7734375 -0.14941,1.4707031 -0.44531,2.0859375 -0.29883,0.609375 -0.72364,1.08691404 -1.27735,1.42968748 -0.54785,0.34570312 -1.17773,0.515625 -1.88672,0.515625 -1.07226,0 -1.94238,-0.375 -2.61328,-1.125 -0.66504,-0.74999998 -0.99609,-1.73730468 -0.99609,-2.96484378 z m 1.35937,0.1523438 c 0,0.8847656 0.20215,1.5908203 0.60938,2.1210937 0.41309,0.5332032 0.96094,0.79687503 1.64062,0.79687503 0.68555,0 1.2334,-0.26953123 1.64063,-0.80859373 0.4043,-0.5390625 0.60937,-1.2919922 0.60937,-2.2617188 0,-0.8730468 -0.208,-1.5820312 -0.62109,-2.1210937 -0.41601,-0.5390625 -0.96094,-0.8085938 -1.64062,-0.8085938 -0.67383,0 -1.21582,0.2666016 -1.62891,0.796875 -0.40723,0.5332032 -0.60938,1.2949219 -0.60938,2.2851563 z m 8.83008,-4.0429688 0.0469,0.9960938 c 0.60058,-0.7646485 1.38867,-1.1484375 2.36719,-1.1484375 1.67871,0 2.52246,0.946289 2.53125,2.8359375 V 6.2500004e-7 h -1.34766 V -5.2499994 c -0.009,-0.5683593 -0.14063,-0.9902343 -0.39844,-1.265625 -0.25195,-0.2724609 -0.65039,-0.4101562 -1.19531,-0.4101562 -0.43945,0 -0.82617,0.1171875 -1.16016,0.3515625 -0.32812,0.234375 -0.58593,0.5449219 -0.77343,0.9257812 V 6.2500004e-7 h -1.34766 V -7.9218744 Z m 0,0"
       style="fill:#484848;fill-opacity:1;fill-rule:nonzero;stroke:none"
       aria-label="Content Dimension"
       transform="matrix(1.3333333,0,0,1.3333333,732.04167,264.49219)"
       clip-path="url(#clipPath25)" />
    <path
       id="path26"
       d="M 4.1939844,-2.3564478 H 10.416641 V -9.790625e-4 H 1.2642969 V -14.227542 H 4.1939844 Z M 16.774063,0.19823969 c -1.555665,0 -2.82129,-0.47460938 -3.796875,-1.42968749 -0.969727,-0.9521484 -1.453125,-2.2177734 -1.453125,-3.796875 v -0.28125 c 0,-1.0546875 0.202148,-1.9980469 0.609375,-2.8359375 0.413085,-0.84375 0.996093,-1.4912109 1.746093,-1.9453127 0.75586,-0.451172 1.617188,-0.679687 2.578125,-0.679687 1.444336,0 2.581055,0.457031 3.410157,1.3710934 0.83496,0.9140625 1.253906,2.2089844 1.253906,3.8789063 v 1.1484375 h -6.738281 c 0.09375,0.6972656 0.36621,1.2509766 0.820312,1.6640625 0.459961,0.4160156 1.042969,0.6210937 1.746094,0.6210937 1.092773,0 1.945312,-0.3896484 2.554687,-1.171875 l 1.382813,1.546875 c -0.421875,0.6035157 -0.996094,1.07226566 -1.722656,1.40625004 -0.720704,0.33398437 -1.517579,0.50390625 -2.390625,0.50390625 z M 16.445938,-8.4736353 c -0.5625,0 -1.019532,0.1875 -1.371094,0.5625 -0.345703,0.375 -0.5625,0.9140625 -0.65625,1.6171875 h 3.925781 v -0.2226563 c -0.01758,-0.6240234 -0.1875,-1.1044921 -0.515625,-1.4414062 -0.322266,-0.3427734 -0.782227,-0.515625 -1.382812,-0.515625 z m 11.982421,5.5546875 c 0,-0.3427734 -0.172851,-0.6123047 -0.515625,-0.8085938 -0.345703,-0.2021484 -0.890625,-0.3808593 -1.640625,-0.5390625 -2.516601,-0.5302734 -3.773437,-1.5996093 -3.773437,-3.2109375 0,-0.9375 0.386719,-1.7167968 1.160156,-2.34375 0.779297,-0.6328124 1.798828,-0.9492184 3.058594,-0.9492184 1.341797,0 2.416992,0.316406 3.222656,0.9492184 0.802735,0.6328125 1.207031,1.453125 1.207031,2.4609375 h -2.824218 c 0,-0.3984375 -0.134766,-0.7294921 -0.398438,-0.9960937 -0.257812,-0.2636719 -0.665039,-0.3984375 -1.21875,-0.3984375 -0.477539,0 -0.84375,0.1113281 -1.101562,0.328125 -0.257813,0.2109375 -0.386719,0.4863281 -0.386719,0.8203125 0,0.3134766 0.146484,0.5683594 0.445312,0.7617187 0.295899,0.1875 0.796875,0.3515625 1.5,0.4921875 0.703125,0.140625 1.291993,0.2988282 1.769532,0.46875 1.491211,0.5478516 2.238281,1.4970704 2.238281,2.8476563 0,0.9609375 -0.416016,1.7431641 -1.242188,2.34374999 -0.829101,0.59472656 -1.895507,0.890625 -3.199218,0.890625 -0.884766,0 -1.669922,-0.15820313 -2.355469,-0.46875 C 23.685195,-0.58984625 23.146133,-1.02344 22.756484,-1.5712916 22.363906,-2.1250025 22.170547,-2.7226587 22.170547,-3.3642603 h 2.671875 c 0.02344,0.5009766 0.205078,0.8876953 0.550781,1.1601562 0.351563,0.2666016 0.814453,0.3984375 1.394531,0.3984375 0.539063,0 0.94336,-0.099609 1.21875,-0.3046875 0.28125,-0.2109375 0.421875,-0.4804687 0.421875,-0.8085937 z m 10.280274,0 c 0,-0.3427734 -0.172852,-0.6123047 -0.515625,-0.8085938 -0.345703,-0.2021484 -0.890625,-0.3808593 -1.640625,-0.5390625 -2.516602,-0.5302734 -3.773438,-1.5996093 -3.773438,-3.2109375 0,-0.9375 0.386719,-1.7167968 1.160157,-2.34375 0.779296,-0.6328124 1.798828,-0.9492184 3.058593,-0.9492184 1.341797,0 2.416993,0.316406 3.222657,0.9492184 0.802734,0.6328125 1.207031,1.453125 1.207031,2.4609375 h -2.824219 c 0,-0.3984375 -0.134766,-0.7294921 -0.398437,-0.9960937 -0.257813,-0.2636719 -0.665039,-0.3984375 -1.21875,-0.3984375 -0.477539,0 -0.84375,0.1113281 -1.101563,0.328125 -0.257812,0.2109375 -0.386719,0.4863281 -0.386719,0.8203125 0,0.3134766 0.146485,0.5683594 0.445313,0.7617187 0.295898,0.1875 0.796875,0.3515625 1.5,0.4921875 0.703125,0.140625 1.291992,0.2988282 1.769531,0.46875 1.491211,0.5478516 2.238281,1.4970704 2.238281,2.8476563 0,0.9609375 -0.416015,1.7431641 -1.242187,2.34374999 -0.829102,0.59472656 -1.895508,0.890625 -3.199219,0.890625 -0.884766,0 -1.669922,-0.15820313 -2.355469,-0.46875 C 33.965469,-0.58984625 33.426406,-1.02344 33.036758,-1.5712916 32.64418,-2.1250025 32.45082,-2.7226587 32.45082,-3.3642603 h 2.671875 c 0.02344,0.5009766 0.205078,0.8876953 0.550782,1.1601562 0.351562,0.2666016 0.814453,0.3984375 1.394531,0.3984375 0.539062,0 0.943359,-0.099609 1.21875,-0.3046875 0.28125,-0.2109375 0.421875,-0.4804687 0.421875,-0.8085937 z m 4.116211,-2.4609375 c 0,-1.0458984 0.199219,-1.9804688 0.597656,-2.8007813 0.404297,-0.8203125 0.987305,-1.4560546 1.746094,-1.9101564 0.764648,-0.451172 1.646484,-0.679687 2.648437,-0.679687 1.420899,0 2.581055,0.439453 3.480469,1.3124997 0.905273,0.8759766 1.412109,2.0625 1.523438,3.5625 l 0.01172,0.7148437 c 0,1.6259766 -0.454101,2.9296875 -1.359375,3.9140625 -0.899414,0.97851566 -2.109375,1.46484379 -3.632812,1.46484379 -1.523438,0 -2.742188,-0.48632813 -3.65625,-1.46484379 -0.908203,-0.9755859 -1.359375,-2.3027343 -1.359375,-3.984375 z m 2.824219,0.1992187 c 0,1.0078125 0.1875,1.7783204 0.5625,2.3085938 0.380859,0.5244141 0.925781,0.7851562 1.628906,0.7851562 0.679687,0 1.209961,-0.2607421 1.59375,-0.7851562 0.380859,-0.5214844 0.574219,-1.359375 0.574219,-2.5078125 0,-0.984375 -0.19336,-1.7460938 -0.574219,-2.2851563 -0.383789,-0.5390625 -0.922852,-0.8085937 -1.617188,-0.8085937 -0.688476,0 -1.224609,0.2695312 -1.605468,0.8085937 -0.375,0.5332032 -0.5625,1.359375 -0.5625,2.484375 z m 11.510742,-5.3906254 0.09375,1.2187504 c 0.75,-0.9433594 1.760742,-1.4179684 3.035156,-1.4179684 1.116211,0 1.948242,0.333984 2.496094,0.9960934 0.544922,0.65625 0.826172,1.6376954 0.84375,2.9414063 V -9.790625e-4 H 60.804336 V -6.7626978 c 0,-0.5917969 -0.134766,-1.0253906 -0.398438,-1.3007813 -0.257812,-0.2724609 -0.688476,-0.4101562 -1.289062,-0.4101562 -0.796875,0 -1.394531,0.3398437 -1.792969,1.0195312 v 7.4531250375 h -2.8125 V -10.571292 Z m 16.696289,5.5546879 V -9.790625e-4 H 70.926406 V -14.227542 h 5.554688 c 1.060547,0 1.998047,0.19629 2.8125,0.585938 0.811523,0.392578 1.435547,0.949219 1.875,1.675781 0.436523,0.720703 0.65625,1.535156 0.65625,2.4492189 0,1.4003907 -0.480469,2.5019532 -1.441406,3.3046875 -0.955079,0.796875 -2.270508,1.1953125 -3.949219,1.1953125 z m 0,-2.3671875 h 2.625 c 0.773437,0 1.362304,-0.1787109 1.769531,-0.5390625 C 78.654922,-8.289065 78.86,-8.8134791 78.86,-9.4931666 c 0,-0.6943354 -0.208008,-1.2568354 -0.621094,-1.6875004 -0.407226,-0.427734 -0.969726,-0.65039 -1.6875,-0.667968 H 73.856094 Z M 86.626602,-9.790625e-4 H 83.790664 V -15.000979 h 2.835938 z m 8.440429,0 C 94.932266,-0.25879156 94.838516,-0.57519781 94.785781,-0.95019781 c -0.688476,0.76757812 -1.579101,1.1484375 -2.671875,1.1484375 -1.03125,0 -1.886718,-0.29882813 -2.566406,-0.90234375 C 88.867813,-1.30469 88.527969,-2.0576197 88.527969,-2.9658228 c 0,-1.125 0.413086,-1.9833984 1.242187,-2.578125 0.826172,-0.6005859 2.027344,-0.9052734 3.597657,-0.9140625 h 1.300781 v -0.609375 c 0,-0.4833984 -0.125977,-0.8701172 -0.375,-1.1601563 C 94.041641,-8.52344 93.649063,-8.6728541 93.11,-8.6728541 c -0.477539,0 -0.852539,0.1142579 -1.125,0.3398438 -0.266602,0.2285156 -0.398437,0.5390625 -0.398437,0.9375 h -2.824219 c 0,-0.609375 0.1875,-1.1748047 0.5625,-1.6992188 0.375,-0.5214843 0.905273,-0.9316409 1.59375,-1.2304689 0.694336,-0.295898 1.470703,-0.445312 2.332031,-0.445312 1.303711,0 2.337891,0.328125 3.105469,0.9843747 0.764648,0.65625 1.148437,1.5791016 1.148437,2.765625 v 4.5820312 c 0,1.0019532 0.140625,1.75781254 0.421875,2.27343754 V -9.790625e-4 Z M 92.735,-1.9697291 c 0.413086,0 0.796875,-0.087891 1.148438,-0.2695312 0.351562,-0.1875 0.612304,-0.4365234 0.785156,-0.75 v -1.8164063 h -1.054688 c -1.415039,0 -2.167968,0.4892579 -2.261718,1.4648438 v 0.1640625 c 0,0.3515625 0.120117,0.6416016 0.363281,0.8671875 0.249023,0.2285156 0.588867,0.3398437 1.019531,0.3398437 z m 9.52441,-8.6015629 0.0937,1.2187504 c 0.75,-0.9433594 1.76075,-1.4179684 3.03516,-1.4179684 1.11621,0 1.94824,0.333984 2.49609,0.9960934 0.54493,0.65625 0.82618,1.6376954 0.84375,2.9414063 V -9.790625e-4 H 105.9039 V -6.7626978 c 0,-0.5917969 -0.13477,-1.0253906 -0.39844,-1.3007813 -0.25781,-0.2724609 -0.68848,-0.4101562 -1.28906,-0.4101562 -0.79688,0 -1.39454,0.3398437 -1.79297,1.0195312 V -9.790625e-4 H 99.610977 V -10.571292 Z m 0,0"
       style="fill:#484848;fill-opacity:1;fill-rule:nonzero;stroke:none"
       aria-label="Lesson Plan"
       transform="matrix(1.3333333,0,0,1.3333333,156.22833,322.86459)"
       clip-path="url(#clipPath27)" />
    <path
       id="path28"
       d="M 7.1259766,-2.7890619 H 2.6611328 L 1.6533203,6.2500004e-7 H 0.21191406 L 4.2783203,-10.664062 H 5.5087891 L 9.5869141,6.2500004e-7 H 8.1455078 Z M 3.0830078,-3.9374994 H 6.7158203 L 4.8994141,-8.9296869 Z m 10.9042972,2.97656253 c 0.483398,0 0.905273,-0.14355473 1.265625,-0.43359373 0.357422,-0.2958985 0.55664,-0.6621094 0.597656,-1.1015625 h 1.289062 c -0.03223,0.4541015 -0.193359,0.8876953 -0.480468,1.3007812 -0.28125,0.40722659 -0.665039,0.73535159 -1.148438,0.98437503 -0.477539,0.24023437 -0.984375,0.36328125 -1.523437,0.36328125 -1.078125,0 -1.939453,-0.35742188 -2.578125,-1.078125 C 10.776367,-1.6523431 10.459961,-2.6396478 10.459961,-3.8906244 v -0.2226562 c 0,-0.7734375 0.140625,-1.4589844 0.421875,-2.0625 0.28125,-0.600586 0.685547,-1.0664063 1.21875,-1.3945313 0.530273,-0.3339843 1.154297,-0.5039062 1.875,-0.5039062 0.890625,0 1.628906,0.2666015 2.214844,0.796875 0.591797,0.5332031 0.908203,1.2246094 0.949218,2.0742187 h -1.289062 c -0.04102,-0.5068359 -0.234375,-0.9257812 -0.585938,-1.2539062 -0.345703,-0.3339844 -0.773437,-0.5039063 -1.289062,-0.5039063 -0.688477,0 -1.224609,0.2519532 -1.605469,0.75 -0.375,0.4921875 -0.5625,1.2070313 -0.5625,2.1445313 v 0.2578125 c 0,0.9140625 0.1875,1.6171875 0.5625,2.109375 0.375,0.4921875 0.914063,0.73828123 1.617188,0.73828123 z m 6.498047,-8.88281253 v 1.921875 h 1.488281 v 1.0429688 h -1.488281 v 4.9101562 c 0,0.3222657 0.06445,0.5625 0.199218,0.7265625 0.131836,0.1582032 0.357422,0.234375 0.679688,0.234375 0.155273,0 0.36914,-0.029297 0.644531,-0.09375 V 6.2500004e-7 C 21.648437,0.09961 21.299805,0.15234438 20.96582,0.15234438 c -0.603515,0 -1.060547,-0.18164063 -1.371093,-0.55078125 -0.304688,-0.36621094 -0.457032,-0.89062503 -0.457032,-1.57031253 v -4.9101562 h -1.441406 v -1.0429688 h 1.441406 v -1.921875 z M 25.011719,6.2500004e-7 H 23.664062 V -7.9218744 h 1.347657 z M 23.546875,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199219,-0.550782 0.140625,-0.155273 0.339843,-0.234375 0.597656,-0.234375 0.263672,0 0.462891,0.0791 0.597656,0.234375 0.140625,0.149414 0.210938,0.333985 0.210938,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210938,0.5507809 -0.134765,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257813,0 -0.457031,-0.073242 -0.597656,-0.2226562 -0.134766,-0.1464844 -0.199219,-0.3310547 -0.199219,-0.5507809 z m 6.243164,8.1914059 1.957031,-6.0820313 h 1.382813 L 30.293945,6.2500004e-7 h -1.03125 L 26.391602,-7.9218744 h 1.382812 z M 35.901367,6.2500004e-7 H 34.553711 V -7.9218744 h 1.347656 z M 34.436523,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199219,-0.550782 0.140625,-0.155273 0.339844,-0.234375 0.597656,-0.234375 0.263672,0 0.462891,0.0791 0.597657,0.234375 0.140625,0.149414 0.210937,0.333985 0.210937,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210937,0.5507809 -0.134766,0.149414 -0.333985,0.2226562 -0.597657,0.2226562 -0.257812,0 -0.457031,-0.073242 -0.597656,-0.2226562 -0.134765,-0.1464844 -0.199219,-0.3310547 -0.199219,-0.5507809 z m 5.458008,0.1874996 v 1.921875 h 1.488281 v 1.0429688 h -1.488281 v 4.9101562 c 0,0.3222657 0.06445,0.5625 0.199219,0.7265625 0.131836,0.1582032 0.357422,0.234375 0.679687,0.234375 0.155274,0 0.369141,-0.029297 0.644532,-0.09375 V 6.2500004e-7 C 41.057617,0.09961 40.708984,0.15234438 40.375,0.15234438 c -0.603516,0 -1.060547,-0.18164063 -1.371094,-0.55078125 -0.304687,-0.36621094 -0.457031,-0.89062503 -0.457031,-1.57031253 v -4.9101562 h -1.441406 v -1.0429688 h 1.441406 v -1.921875 z M 44.420898,6.2500004e-7 H 43.073242 V -7.9218744 h 1.347656 z M 42.956055,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199218,-0.550782 0.140625,-0.155273 0.339844,-0.234375 0.597657,-0.234375 0.263672,0 0.46289,0.0791 0.597656,0.234375 0.140625,0.149414 0.210937,0.333985 0.210937,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210937,0.5507809 -0.134766,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257813,0 -0.457032,-0.073242 -0.597657,-0.2226562 -0.134765,-0.1464844 -0.199218,-0.3310547 -0.199218,-0.5507809 z m 6.911132,10.18359338 c -1.072265,0 -1.945312,-0.3515625 -2.625,-1.0546875 C 46.568359,-1.6113275 46.234375,-2.5576166 46.234375,-3.7382806 v -0.2578125 c 0,-0.7792969 0.146484,-1.4794922 0.445312,-2.0976563 0.304688,-0.6152343 0.726563,-1.1015625 1.265625,-1.453125 0.539063,-0.3515625 1.125,-0.5273437 1.757813,-0.5273437 1.03125,0 1.831055,0.3398437 2.402344,1.0195312 0.568359,0.6796875 0.855468,1.6523438 0.855468,2.9179688 v 0.5625 H 47.59375 c 0.01465,0.7822265 0.240234,1.415039 0.679687,1.8984375 0.436524,0.477539 0.990235,0.71484373 1.664063,0.71484373 0.483398,0 0.890625,-0.0966797 1.21875,-0.29296873 0.333984,-0.1933594 0.626953,-0.4511719 0.878906,-0.7734375 l 0.820313,0.6445312 C 52.19043,-0.35742125 51.194336,0.15234438 49.867187,0.15234438 Z M 49.703125,-6.9609369 c -0.547852,0 -1.007813,0.1992188 -1.382813,0.5976563 -0.36914,0.3984375 -0.594726,0.9580078 -0.679687,1.6757812 h 3.960937 v -0.1054687 c -0.04102,-0.6855469 -0.228515,-1.21875 -0.5625,-1.59375 -0.328125,-0.3808594 -0.773437,-0.5742188 -1.335937,-0.5742188 z m 9.424805,4.8632813 c 0,-0.366211 -0.137696,-0.6503906 -0.410157,-0.8554688 -0.27539,-0.2021484 -0.755859,-0.3779297 -1.441406,-0.5273437 -0.688476,-0.1464844 -1.236328,-0.3222656 -1.640625,-0.5273438 -0.398437,-0.2021484 -0.697265,-0.4453125 -0.890625,-0.7265625 -0.1875,-0.2871093 -0.28125,-0.6269531 -0.28125,-1.0195312 0,-0.647461 0.272461,-1.1953125 0.820313,-1.640625 0.544922,-0.4511719 1.248047,-0.6796875 2.109375,-0.6796875 0.896484,0 1.623047,0.234375 2.179687,0.703125 0.5625,0.4628906 0.84375,1.0517578 0.84375,1.7695312 h -1.371094 c 0,-0.3662109 -0.158203,-0.6826172 -0.46875,-0.9492187 -0.313476,-0.272461 -0.708984,-0.4101563 -1.183593,-0.4101563 -0.500977,0 -0.890625,0.1113282 -1.171875,0.328125 -0.275391,0.2109375 -0.410157,0.4921875 -0.410157,0.84375 0,0.3222657 0.128907,0.5683594 0.386719,0.7382813 0.257813,0.1640625 0.726563,0.3251953 1.40625,0.4804687 0.679688,0.1494141 1.22461,0.328125 1.640625,0.5390625 0.421875,0.2050782 0.732422,0.4541016 0.9375,0.75 0.202149,0.2988282 0.304688,0.65625 0.304688,1.078125 0,0.7119141 -0.28711,1.28320315 -0.855469,1.71093753 -0.5625,0.43066406 -1.297852,0.64453125 -2.203125,0.64453125 -0.632813,0 -1.195313,-0.11425782 -1.6875,-0.33984375 -0.486328,-0.22558594 -0.867188,-0.5390625 -1.148438,-0.93750003 -0.27539,-0.4042968 -0.410156,-0.84375 -0.410156,-1.3125 h 1.359375 c 0.02344,0.4541016 0.202149,0.8144532 0.539063,1.078125 0.342773,0.2666016 0.791015,0.39843753 1.347656,0.39843753 0.515625,0 0.925781,-0.0996093 1.230469,-0.30468753 0.310547,-0.2109375 0.46875,-0.4863281 0.46875,-0.8320312 z M 70.837891,6.2500004e-7 C 70.758789,-0.15527281 70.697266,-0.43359312 70.650391,-0.83203062 c -0.632813,0.65625 -1.388672,0.984375 -2.261719,0.984375 -0.782227,0 -1.423828,-0.22265625 -1.921875,-0.66796875 -0.500977,-0.4453125 -0.75,-1.00781253 -0.75,-1.68750003 0,-0.8203125 0.310547,-1.4560547 0.9375,-1.9101562 0.632812,-0.459961 1.514648,-0.6914063 2.648437,-0.6914063 h 1.324219 v -0.6210937 c 0,-0.4746094 -0.146484,-0.8554688 -0.433594,-1.1367188 -0.28125,-0.28125 -0.697265,-0.421875 -1.242187,-0.421875 -0.486328,0 -0.890625,0.1259766 -1.21875,0.375 -0.328125,0.2431641 -0.492188,0.5361328 -0.492188,0.8789063 h -1.359375 c 0,-0.3896485 0.140625,-0.7675781 0.421875,-1.1367188 0.28125,-0.375 0.65918,-0.6679687 1.136719,-0.8789062 0.483399,-0.2167969 1.013672,-0.328125 1.59375,-0.328125 0.914063,0 1.628906,0.2314453 2.144531,0.6914062 0.515625,0.4541016 0.785157,1.0839844 0.808594,1.8867188 v 3.6445312 c 0,0.7265625 0.08789,1.30664065 0.269531,1.73437503 V 6.2500004e-7 Z M 68.587891,-1.0312494 c 0.427734,0 0.832031,-0.1083984 1.207031,-0.328125 0.380859,-0.2167968 0.65918,-0.5039062 0.832031,-0.8554687 v -1.6289063 h -1.066406 c -1.658203,0 -2.484375,0.4863282 -2.484375,1.453125 0,0.4306641 0.140625,0.7675782 0.421875,1.0078125 0.28125,0.234375 0.644531,0.3515625 1.089844,0.3515625 z m 6.785156,-6.890625 0.04687,0.9960938 c 0.600586,-0.7646485 1.388672,-1.1484375 2.367187,-1.1484375 1.678711,0 2.522461,0.946289 2.53125,2.8359375 V 6.2500004e-7 H 78.970703 V -5.2499994 c -0.0088,-0.5683593 -0.140625,-0.9902343 -0.398437,-1.265625 -0.251954,-0.2724609 -0.650391,-0.4101562 -1.195313,-0.4101562 -0.439453,0 -0.826172,0.1171875 -1.160156,0.3515625 -0.328125,0.234375 -0.585938,0.5449219 -0.773438,0.9257812 V 6.2500004e-7 H 74.095703 V -7.9218744 Z m 6.647461,3.890625 c 0,-1.2099609 0.287109,-2.1855468 0.867187,-2.9296875 0.577149,-0.7412109 1.330078,-1.1132812 2.261719,-1.1132812 0.928711,0 1.664063,0.3164062 2.203125,0.9492187 v -4.1249996 h 1.359375 V 6.2500004e-7 H 87.469727 L 87.399414,-0.85546812 c -0.539062,0.67382812 -1.294922,1.0078125 -2.261719,1.0078125 -0.914062,0 -1.664062,-0.375 -2.25,-1.125 C 82.307617,-1.728515 82.020508,-2.71289 82.020508,-3.9257806 Z m 1.359375,0.1523438 c 0,0.899414 0.18164,1.602539 0.550781,2.109375 0.375,0.5097656 0.890625,0.7617187 1.546875,0.7617187 0.858398,0 1.482422,-0.3808593 1.875,-1.1484375 v -3.6445312 c -0.398437,-0.75 -1.019531,-1.125 -1.863281,-1.125 -0.665039,0 -1.183594,0.2578125 -1.558594,0.7734375 -0.369141,0.515625 -0.550781,1.274414 -0.550781,2.2734375 z m 12.75,2.7304687 h 5.062497 V 6.2500004e-7 H 94.723633 V -10.664062 h 1.40625 z m 9.732417,1.30078128 c -1.07226,0 -1.94531,-0.3515625 -2.625,-1.0546875 -0.67382,-0.70898438 -1.00781,-1.65527348 -1.00781,-2.83593748 v -0.2578125 c 0,-0.7792969 0.14649,-1.4794922 0.44531,-2.0976563 0.30469,-0.6152343 0.72657,-1.1015625 1.26563,-1.453125 0.53906,-0.3515625 1.125,-0.5273437 1.75781,-0.5273437 1.03125,0 1.83106,0.3398437 2.40235,1.0195312 0.56836,0.6796875 0.85546,1.6523438 0.85546,2.9179688 v 0.5625 h -5.36718 c 0.0147,0.7822265 0.24023,1.415039 0.67968,1.8984375 0.43653,0.477539 0.99024,0.71484373 1.66407,0.71484373 0.4834,0 0.89062,-0.0966797 1.21875,-0.29296873 0.33398,-0.1933594 0.62695,-0.4511719 0.8789,-0.7734375 l 0.82032,0.6445312 c -0.66504,1.02539065 -1.66114,1.53515628 -2.98829,1.53515628 z m -0.16406,-7.11328128 c -0.54785,0 -1.00781,0.1992188 -1.38281,0.5976563 -0.36914,0.3984375 -0.59473,0.9580078 -0.67969,1.6757812 h 3.96094 v -0.1054687 c -0.041,-0.6855469 -0.22852,-1.21875 -0.5625,-1.59375 -0.32813,-0.3808594 -0.77344,-0.5742188 -1.33594,-0.5742188 z M 115.4043,6.2500004e-7 C 115.3252,-0.15527281 115.26367,-0.43359312 115.2168,-0.83203062 c -0.63282,0.65625 -1.38867,0.984375 -2.26172,0.984375 -0.78223,0 -1.42383,-0.22265625 -1.92188,-0.66796875 -0.50097,-0.4453125 -0.75,-1.00781253 -0.75,-1.68750003 0,-0.8203125 0.31055,-1.4560547 0.9375,-1.9101562 0.63282,-0.459961 1.51465,-0.6914063 2.64844,-0.6914063 h 1.32422 v -0.6210937 c 0,-0.4746094 -0.14648,-0.8554688 -0.43359,-1.1367188 -0.28125,-0.28125 -0.69727,-0.421875 -1.24219,-0.421875 -0.48633,0 -0.89063,0.1259766 -1.21875,0.375 -0.32813,0.2431641 -0.49219,0.5361328 -0.49219,0.8789063 h -1.35937 c 0,-0.3896485 0.14062,-0.7675781 0.42187,-1.1367188 0.28125,-0.375 0.65918,-0.6679687 1.13672,-0.8789062 0.4834,-0.2167969 1.01367,-0.328125 1.59375,-0.328125 0.91406,0 1.62891,0.2314453 2.14453,0.6914062 0.51563,0.4541016 0.78516,1.0839844 0.80859,1.8867188 v 3.6445312 c 0,0.7265625 0.0879,1.30664065 0.26954,1.73437503 V 6.2500004e-7 Z M 113.1543,-1.0312494 c 0.42773,0 0.83203,-0.1083984 1.20703,-0.328125 0.38086,-0.2167968 0.65918,-0.5039062 0.83203,-0.8554687 v -1.6289063 h -1.06641 c -1.6582,0 -2.48437,0.4863282 -2.48437,1.453125 0,0.4306641 0.14062,0.7675782 0.42187,1.0078125 0.28125,0.234375 0.64453,0.3515625 1.08985,0.3515625 z m 9.32812,-5.6835937 c -0.20508,-0.029297 -0.42187,-0.046875 -0.65625,-0.046875 -0.89062,0 -1.49707,0.3808594 -1.8164,1.1367187 V 6.2500004e-7 h -1.34766 V -7.9218744 h 1.3125 l 0.0234,0.9140625 c 0.44531,-0.7089843 1.07226,-1.0664062 1.88672,-1.0664062 0.26367,0 0.46289,0.035156 0.59765,0.1054687 z m 2.52539,-1.2070313 0.0469,0.9960938 c 0.60058,-0.7646485 1.38867,-1.1484375 2.36719,-1.1484375 1.67871,0 2.52246,0.946289 2.53124,2.8359375 V 6.2500004e-7 h -1.34765 V -5.2499994 c -0.009,-0.5683593 -0.14063,-0.9902343 -0.39844,-1.265625 -0.25195,-0.2724609 -0.65039,-0.4101562 -1.19531,-0.4101562 -0.43945,0 -0.82617,0.1171875 -1.16016,0.3515625 -0.32812,0.234375 -0.58593,0.5449219 -0.77343,0.9257812 V 6.2500004e-7 h -1.34766 V -7.9218744 Z M 133.45996,6.2500004e-7 H 132.1123 V -7.9218744 h 1.34766 z M 131.99512,-10.031249 c 0,-0.216797 0.0645,-0.401368 0.19922,-0.550782 0.14062,-0.155273 0.33984,-0.234375 0.59765,-0.234375 0.26367,0 0.46289,0.0791 0.59766,0.234375 0.14062,0.149414 0.21094,0.333985 0.21094,0.550782 0,0.2197262 -0.0703,0.4042965 -0.21094,0.5507809 -0.13477,0.149414 -0.33399,0.2226562 -0.59766,0.2226562 -0.25781,0 -0.45703,-0.073242 -0.59765,-0.2226562 -0.13477,-0.1464844 -0.19922,-0.3310547 -0.19922,-0.5507809 z m 4.90722,2.1093746 0.0469,0.9960938 c 0.60058,-0.7646485 1.38867,-1.1484375 2.36719,-1.1484375 1.67871,0 2.52246,0.946289 2.53125,2.8359375 V 6.2500004e-7 H 140.5 V -5.2499994 c -0.009,-0.5683593 -0.14063,-0.9902343 -0.39844,-1.265625 -0.25195,-0.2724609 -0.65039,-0.4101562 -1.19531,-0.4101562 -0.43945,0 -0.82617,0.1171875 -1.16016,0.3515625 -0.32812,0.234375 -0.58593,0.5449219 -0.77343,0.9257812 V 6.2500004e-7 H 135.625 V -7.9218744 Z m 6.66211,3.890625 c 0,-1.2333984 0.28418,-2.2148437 0.85547,-2.9414062 0.56836,-0.7324219 1.32715,-1.1015625 2.27344,-1.1015625 0.9668,0 1.72266,0.3457031 2.26172,1.03125 l 0.0703,-0.8789063 h 1.23047 v 7.73437503 c 0,1.02246093 -0.30469,1.82812497 -0.91406,2.41406247 -0.60352,0.5917969 -1.41797,0.890625 -2.44922,0.890625 -0.57129,0 -1.13086,-0.1230468 -1.67578,-0.3632812 -0.54785,-0.2431641 -0.9668,-0.5800781 -1.25391,-1.0078125 l 0.70313,-0.80859377 c 0.58593,0.71777347 1.29492,1.07812497 2.13281,1.07812497 0.66211,0 1.17773,-0.1875 1.54687,-0.5625 0.36621,-0.3691406 0.55078,-0.88769529 0.55078,-1.55859372 v -0.69140625 c -0.53906,0.6328125 -1.27734,0.94921875 -2.21484,0.94921875 -0.93164,0 -1.68457,-0.375 -2.26172,-1.125 -0.57129,-0.74999998 -0.85547,-1.76953128 -0.85547,-3.05859378 z m 1.35938,0.1523438 c 0,0.899414 0.18164,1.602539 0.55078,2.109375 0.36621,0.5097656 0.87891,0.7617187 1.53516,0.7617187 0.85839,0 1.48828,-0.3867187 1.88671,-1.1601562 v -3.6210938 c -0.41601,-0.7558593 -1.03711,-1.1367187 -1.86328,-1.1367187 -0.66504,0 -1.18359,0.2578125 -1.55859,0.7734375 -0.36914,0.515625 -0.55078,1.274414 -0.55078,2.2734375 z m 0,0"
       style="fill:#484848;fill-opacity:1;fill-rule:nonzero;stroke:none"
       aria-label="Activities and Learning"
       transform="matrix(1.3333333,0,0,1.3333333,732.04167,364.49219)"
       clip-path="url(#clipPath29)" />
    <path
       id="path30"
       d="m 9.4462891,-4.9921869 c 0,1.0488282 -0.1757813,1.9628907 -0.5273438,2.7421875 -0.3515625,0.7734375 -0.852539,1.36816409 -1.5,1.78125003 -0.6416016,0.41601562 -1.3916016,0.62109375 -2.25,0.62109375 -0.84375,0 -1.5908203,-0.20507813 -2.2382812,-0.62109375 C 2.2802734,-0.88183531 1.7763672,-1.4707025 1.4189453,-2.2382806 1.0585937,-3.0029291 0.87402344,-3.8906244 0.86816406,-4.8984369 v -0.7617187 c 0,-1.022461 0.17578124,-1.9277344 0.52734374,-2.71875 0.3574219,-0.788086 0.8613281,-1.3886719 1.5117188,-1.8046874 0.65625,-0.421875 1.4003906,-0.632813 2.2382812,-0.632813 0.8583984,0 1.6113281,0.208008 2.2617188,0.621094 0.65625,0.4160158 1.1601562,1.0166017 1.5117187,1.8046876 0.3515625,0.7822266 0.5273438,1.6933594 0.5273438,2.7304688 z m -1.40625,-0.6796875 c 0,-1.265625 -0.2548829,-2.2324218 -0.7617188,-2.90625 -0.5097656,-0.6796875 -1.21875,-1.0195312 -2.1328125,-1.0195312 -0.8847656,0 -1.5820312,0.3398437 -2.0976562,1.0195312 -0.5097657,0.6738282 -0.7705078,1.6054688 -0.7851563,2.8007813 v 0.7851562 c 0,1.2275391 0.2578125,2.1914063 0.7734375,2.8945313 0.515625,0.703125 1.2246094,1.0546875 2.1328125,1.0546875 0.9052734,0 1.6054688,-0.3310547 2.0976563,-0.9960938 0.4980468,-0.6621093 0.7558593,-1.6113281 0.7734375,-2.8476562 z m 8.1826169,4.88671878 c -0.524414,0.62695312 -1.297851,0.9375 -2.320312,0.9375 -0.84375,0 -1.488281,-0.24609375 -1.933594,-0.73828125 C 11.529297,-1.0781244 11.306641,-1.8046869 11.300781,-2.7656244 v -5.15625 h 1.359375 v 5.1210938 c 0,1.1953125 0.486328,1.7929687 1.464844,1.7929687 1.03125,0 1.716797,-0.3808593 2.0625,-1.1484375 v -5.765625 h 1.359375 V 6.2500004e-7 h -1.289063 z m 5.206055,-9.05859378 v 1.921875 h 1.488281 v 1.0429688 h -1.488281 v 4.9101562 c 0,0.3222657 0.06445,0.5625 0.199219,0.7265625 0.131836,0.1582032 0.357422,0.234375 0.679687,0.234375 0.155274,0 0.369141,-0.029297 0.644531,-0.09375 V 6.2500004e-7 C 22.591797,0.09961 22.243164,0.15234438 21.90918,0.15234438 c -0.603516,0 -1.060547,-0.18164063 -1.371094,-0.55078125 -0.304688,-0.36621094 -0.457031,-0.89062503 -0.457031,-1.57031253 v -4.9101562 h -1.441407 v -1.0429688 h 1.441407 v -1.921875 z m 6.237305,8.88281253 c 0.483398,0 0.905273,-0.14355473 1.265625,-0.43359373 0.357421,-0.2958985 0.55664,-0.6621094 0.597656,-1.1015625 h 1.289062 c -0.03223,0.4541015 -0.193359,0.8876953 -0.480468,1.3007812 -0.28125,0.40722659 -0.665039,0.73535159 -1.148438,0.98437503 -0.477539,0.24023437 -0.984375,0.36328125 -1.523437,0.36328125 -1.078125,0 -1.939454,-0.35742188 -2.578125,-1.078125 C 24.455078,-1.6523431 24.138672,-2.6396478 24.138672,-3.8906244 v -0.2226562 c 0,-0.7734375 0.140625,-1.4589844 0.421875,-2.0625 0.28125,-0.600586 0.685547,-1.0664063 1.21875,-1.3945313 0.530273,-0.3339843 1.154297,-0.5039062 1.875,-0.5039062 0.890625,0 1.628906,0.2666015 2.214844,0.796875 0.591796,0.5332031 0.908203,1.2246094 0.949218,2.0742187 h -1.289062 c -0.04102,-0.5068359 -0.234375,-0.9257812 -0.585938,-1.2539062 -0.345703,-0.3339844 -0.773437,-0.5039063 -1.289062,-0.5039063 -0.688477,0 -1.22461,0.2519532 -1.605469,0.75 -0.375,0.4921875 -0.5625,1.2070313 -0.5625,2.1445313 v 0.2578125 c 0,0.9140625 0.1875,1.6171875 0.5625,2.109375 0.375,0.4921875 0.914063,0.73828123 1.617188,0.73828123 z m 4.30664,-3.07031253 c 0,-0.7792968 0.152344,-1.4794922 0.457031,-2.0976562 0.304688,-0.6240235 0.726563,-1.1044922 1.265625,-1.4414063 0.544922,-0.3339843 1.171875,-0.5039062 1.875,-0.5039062 1.078125,0 1.948243,0.375 2.613282,1.125 0.670898,0.7441406 1.007812,1.734375 1.007812,2.9765625 v 0.09375 c 0,0.7734375 -0.149414,1.4707031 -0.445312,2.0859375 -0.298828,0.609375 -0.723633,1.08691404 -1.277344,1.42968748 -0.547852,0.34570312 -1.177734,0.515625 -1.886719,0.515625 -1.072265,0 -1.942383,-0.375 -2.613281,-1.125 C 32.303711,-1.7226556 31.972656,-2.7099603 31.972656,-3.9374994 Z m 1.359375,0.1523438 c 0,0.8847656 0.202149,1.5908203 0.609375,2.1210937 0.413086,0.5332032 0.960938,0.79687503 1.640625,0.79687503 0.685547,0 1.233399,-0.26953123 1.640625,-0.80859373 0.404297,-0.5390625 0.609375,-1.2919922 0.609375,-2.2617188 0,-0.8730468 -0.208008,-1.5820312 -0.621094,-2.1210937 -0.416015,-0.5390625 -0.960937,-0.8085938 -1.640625,-0.8085938 -0.673828,0 -1.21582,0.2666016 -1.628906,0.796875 -0.407226,0.5332032 -0.609375,1.2949219 -0.609375,2.2851563 z m 8.821289,-4.0429688 0.03516,0.8789063 c 0.585937,-0.6855469 1.371093,-1.03125 2.355468,-1.03125 1.107422,0 1.863282,0.4277344 2.261719,1.2773437 0.263672,-0.3808593 0.609375,-0.6914062 1.03125,-0.9257812 0.421875,-0.234375 0.919922,-0.3515625 1.5,-0.3515625 1.734375,0 2.616211,0.9228515 2.648438,2.765625 V 6.2500004e-7 H 50.625977 V -5.2265619 c 0,-0.5683593 -0.128907,-0.9960937 -0.386719,-1.2773437 -0.257813,-0.28125 -0.691406,-0.421875 -1.300781,-0.421875 -0.500977,0 -0.919922,0.1523437 -1.253907,0.4570312 -0.328125,0.2988282 -0.521484,0.7001953 -0.574218,1.2070313 V 6.2500004e-7 H 45.750977 V -5.1914056 c 0,-1.1542969 -0.56836,-1.734375 -1.699219,-1.734375 -0.890625,0 -1.497071,0.3808594 -1.816406,1.1367187 V 6.2500004e-7 H 40.875977 V -7.9218744 Z m 15.155274,8.07421878 c -1.072266,0 -1.945313,-0.3515625 -2.625,-1.0546875 C 54.009766,-1.6113275 53.675781,-2.5576166 53.675781,-3.7382806 v -0.2578125 c 0,-0.7792969 0.146485,-1.4794922 0.445313,-2.0976563 0.304687,-0.6152343 0.726562,-1.1015625 1.265625,-1.453125 0.539062,-0.3515625 1.125,-0.5273437 1.757812,-0.5273437 1.03125,0 1.831055,0.3398437 2.402344,1.0195312 0.568359,0.6796875 0.855469,1.6523438 0.855469,2.9179688 v 0.5625 h -5.367188 c 0.01465,0.7822265 0.240235,1.415039 0.679688,1.8984375 0.436523,0.477539 0.990234,0.71484373 1.664062,0.71484373 0.483399,0 0.890625,-0.0966797 1.21875,-0.29296873 0.333985,-0.1933594 0.626953,-0.4511719 0.878906,-0.7734375 l 0.820313,0.6445312 c -0.665039,1.02539065 -1.661133,1.53515628 -2.988281,1.53515628 z M 57.144531,-6.9609369 c -0.547851,0 -1.007812,0.1992188 -1.382812,0.5976563 -0.369141,0.3984375 -0.594727,0.9580078 -0.679688,1.6757812 h 3.960938 v -0.1054687 c -0.04102,-0.6855469 -0.228516,-1.21875 -0.5625,-1.59375 -0.328125,-0.3808594 -0.773438,-0.5742188 -1.335938,-0.5742188 z m 9.421875,4.8632813 c 0,-0.366211 -0.137695,-0.6503906 -0.410156,-0.8554688 -0.275391,-0.2021484 -0.755859,-0.3779297 -1.441406,-0.5273437 -0.688477,-0.1464844 -1.236328,-0.3222656 -1.640625,-0.5273438 -0.398438,-0.2021484 -0.697266,-0.4453125 -0.890625,-0.7265625 -0.1875,-0.2871093 -0.28125,-0.6269531 -0.28125,-1.0195312 0,-0.647461 0.272461,-1.1953125 0.820312,-1.640625 0.544922,-0.4511719 1.248047,-0.6796875 2.109375,-0.6796875 0.896485,0 1.623047,0.234375 2.179688,0.703125 0.5625,0.4628906 0.84375,1.0517578 0.84375,1.7695312 h -1.371094 c 0,-0.3662109 -0.158203,-0.6826172 -0.46875,-0.9492187 -0.313477,-0.272461 -0.708984,-0.4101563 -1.183594,-0.4101563 -0.500976,0 -0.890625,0.1113282 -1.171875,0.328125 -0.27539,0.2109375 -0.410156,0.4921875 -0.410156,0.84375 0,0.3222657 0.128906,0.5683594 0.386719,0.7382813 0.257812,0.1640625 0.726562,0.3251953 1.40625,0.4804687 0.679687,0.1494141 1.224609,0.328125 1.640625,0.5390625 0.421875,0.2050782 0.732422,0.4541016 0.9375,0.75 0.202148,0.2988282 0.304687,0.65625 0.304687,1.078125 0,0.7119141 -0.287109,1.28320315 -0.855469,1.71093753 -0.5625,0.43066406 -1.297851,0.64453125 -2.203125,0.64453125 -0.632812,0 -1.195312,-0.11425782 -1.6875,-0.33984375 -0.486328,-0.22558594 -0.867187,-0.5390625 -1.148437,-0.93750003 -0.275391,-0.4042968 -0.410156,-0.84375 -0.410156,-1.3125 h 1.359375 c 0.02344,0.4541016 0.202148,0.8144532 0.539062,1.078125 0.342774,0.2666016 0.791016,0.39843753 1.347656,0.39843753 0.515625,0 0.925782,-0.0996093 1.230469,-0.30468753 0.310547,-0.2109375 0.46875,-0.4863281 0.46875,-0.8320312 z m 0,0"
       style="fill:#484848;fill-opacity:1;fill-rule:nonzero;stroke:none"
       aria-label="Outcomes"
       transform="matrix(1.3333333,0,0,1.3333333,732.04167,388.49219)"
       clip-path="url(#clipPath31)" />
    <path
       id="path32"
       d="m 9.4462891,-4.9921869 c 0,1.0488282 -0.1757813,1.9628907 -0.5273438,2.7421875 -0.3515625,0.7734375 -0.852539,1.36816409 -1.5,1.78125003 -0.6416016,0.41601562 -1.3916016,0.62109375 -2.25,0.62109375 -0.84375,0 -1.5908203,-0.20507813 -2.2382812,-0.62109375 C 2.2802734,-0.88183531 1.7763672,-1.4707025 1.4189453,-2.2382806 1.0585937,-3.0029291 0.87402344,-3.8906244 0.86816406,-4.8984369 v -0.7617187 c 0,-1.022461 0.17578124,-1.9277344 0.52734374,-2.71875 0.3574219,-0.788086 0.8613281,-1.3886719 1.5117188,-1.8046874 0.65625,-0.421875 1.4003906,-0.632813 2.2382812,-0.632813 0.8583984,0 1.6113281,0.208008 2.2617188,0.621094 0.65625,0.4160158 1.1601562,1.0166017 1.5117187,1.8046876 0.3515625,0.7822266 0.5273438,1.6933594 0.5273438,2.7304688 z m -1.40625,-0.6796875 c 0,-1.265625 -0.2548829,-2.2324218 -0.7617188,-2.90625 -0.5097656,-0.6796875 -1.21875,-1.0195312 -2.1328125,-1.0195312 -0.8847656,0 -1.5820312,0.3398437 -2.0976562,1.0195312 -0.5097657,0.6738282 -0.7705078,1.6054688 -0.7851563,2.8007813 v 0.7851562 c 0,1.2275391 0.2578125,2.1914063 0.7734375,2.8945313 0.515625,0.703125 1.2246094,1.0546875 2.1328125,1.0546875 0.9052734,0 1.6054688,-0.3310547 2.0976563,-0.9960938 C 7.7646484,-2.7011712 8.0224609,-3.65039 8.0400391,-4.8867181 Z M 15.15625,-6.7148431 C 14.951172,-6.74414 14.734375,-6.7617181 14.5,-6.7617181 c -0.890625,0 -1.49707,0.3808594 -1.816406,1.1367187 V 6.2500004e-7 H 11.335938 V -7.9218744 h 1.3125 l 0.02344,0.9140625 c 0.445313,-0.7089843 1.072266,-1.0664062 1.886719,-1.0664062 0.263672,0 0.46289,0.035156 0.597656,0.1054687 z m 0.922852,2.6835937 c 0,-1.2333984 0.284179,-2.2148437 0.855468,-2.9414062 0.56836,-0.7324219 1.327149,-1.1015625 2.273438,-1.1015625 0.966797,0 1.722656,0.3457031 2.261719,1.03125 l 0.07031,-0.8789063 h 1.230469 v 7.73437503 c 0,1.02246093 -0.304688,1.82812497 -0.914063,2.41406247 -0.603515,0.5917969 -1.417968,0.890625 -2.449218,0.890625 -0.57129,0 -1.13086,-0.1230468 -1.675782,-0.3632812 C 17.183594,2.5107428 16.764648,2.1738288 16.477539,1.7460944 l 0.703125,-0.80859377 c 0.585938,0.71777347 1.294922,1.07812497 2.132813,1.07812497 0.662109,0 1.177734,-0.1875 1.546875,-0.5625 0.36621,-0.3691406 0.550781,-0.88769529 0.550781,-1.55859372 v -0.69140625 c -0.539063,0.6328125 -1.277344,0.94921875 -2.214844,0.94921875 -0.931641,0 -1.68457,-0.375 -2.261719,-1.125 C 16.363281,-1.7226556 16.079102,-2.7421869 16.079102,-4.0312494 Z m 1.359375,0.1523438 c 0,0.899414 0.18164,1.602539 0.550781,2.109375 0.366211,0.5097656 0.878906,0.7617187 1.535156,0.7617187 0.858398,0 1.488281,-0.3867187 1.886719,-1.1601562 v -3.6210938 c -0.416016,-0.7558593 -1.03711,-1.1367187 -1.863281,-1.1367187 -0.66504,0 -1.183594,0.2578125 -1.558594,0.7734375 -0.369141,0.515625 -0.550781,1.274414 -0.550781,2.2734375 z M 29.708008,6.2500004e-7 C 29.628906,-0.15527281 29.567383,-0.43359312 29.520508,-0.83203062 c -0.632813,0.65625 -1.388672,0.984375 -2.261719,0.984375 -0.782227,0 -1.423828,-0.22265625 -1.921875,-0.66796875 -0.500977,-0.4453125 -0.75,-1.00781253 -0.75,-1.68750003 0,-0.8203125 0.310547,-1.4560547 0.9375,-1.9101562 0.632813,-0.459961 1.514648,-0.6914063 2.648438,-0.6914063 h 1.324218 v -0.6210937 c 0,-0.4746094 -0.146484,-0.8554688 -0.433593,-1.1367188 -0.28125,-0.28125 -0.697266,-0.421875 -1.242188,-0.421875 -0.486328,0 -0.890625,0.1259766 -1.21875,0.375 -0.328125,0.2431641 -0.492187,0.5361328 -0.492187,0.8789063 h -1.359375 c 0,-0.3896485 0.140625,-0.7675781 0.421875,-1.1367188 0.28125,-0.375 0.659179,-0.6679687 1.136718,-0.8789062 0.483399,-0.2167969 1.013672,-0.328125 1.59375,-0.328125 0.914063,0 1.628907,0.2314453 2.144532,0.6914062 0.515625,0.4541016 0.785156,1.0839844 0.808593,1.8867188 v 3.6445312 c 0,0.7265625 0.08789,1.30664065 0.269532,1.73437503 V 6.2500004e-7 Z M 27.458008,-1.0312494 c 0.427734,0 0.832031,-0.1083984 1.207031,-0.328125 0.380859,-0.2167968 0.65918,-0.5039062 0.832031,-0.8554687 v -1.6289063 h -1.066406 c -1.658203,0 -2.484375,0.4863282 -2.484375,1.453125 0,0.4306641 0.140625,0.7675782 0.421875,1.0078125 0.28125,0.234375 0.644531,0.3515625 1.089844,0.3515625 z m 6.785156,-6.890625 0.04687,0.9960938 c 0.600586,-0.7646485 1.388672,-1.1484375 2.367188,-1.1484375 1.67871,0 2.52246,0.946289 2.53125,2.8359375 V 6.2500004e-7 H 37.84082 V -5.2499994 c -0.0088,-0.5683593 -0.140625,-0.9902343 -0.398437,-1.265625 -0.251953,-0.2724609 -0.650391,-0.4101562 -1.195313,-0.4101562 -0.439453,0 -0.826172,0.1171875 -1.160156,0.3515625 -0.328125,0.234375 -0.585937,0.5449219 -0.773437,0.9257812 V 6.2500004e-7 H 32.96582 V -7.9218744 Z M 42.695312,6.2500004e-7 H 41.347656 V -7.9218744 h 1.347656 z M 41.230469,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199218,-0.550782 0.140625,-0.155273 0.339844,-0.234375 0.597657,-0.234375 0.263672,0 0.46289,0.0791 0.597656,0.234375 0.140625,0.149414 0.210937,0.333985 0.210937,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210937,0.5507809 -0.134766,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257813,0 -0.457032,-0.073242 -0.597657,-0.2226562 -0.134765,-0.1464844 -0.199218,-0.3310547 -0.199218,-0.5507809 z m 4.895508,8.9296871 h 4.640625 V 6.2500004e-7 H 44.473633 V -0.99609312 l 4.371094,-5.81249998 h -4.300782 v -1.1132813 h 6 v 0.9609375 z M 57.173828,6.2500004e-7 C 57.094727,-0.15527281 57.033203,-0.43359312 56.986328,-0.83203062 c -0.632812,0.65625 -1.388672,0.984375 -2.261719,0.984375 -0.782226,0 -1.423828,-0.22265625 -1.921875,-0.66796875 -0.500976,-0.4453125 -0.75,-1.00781253 -0.75,-1.68750003 0,-0.8203125 0.310547,-1.4560547 0.9375,-1.9101562 0.632813,-0.459961 1.514649,-0.6914063 2.648438,-0.6914063 h 1.324219 v -0.6210937 c 0,-0.4746094 -0.146485,-0.8554688 -0.433594,-1.1367188 -0.28125,-0.28125 -0.697266,-0.421875 -1.242188,-0.421875 -0.486328,0 -0.890625,0.1259766 -1.21875,0.375 -0.328125,0.2431641 -0.492187,0.5361328 -0.492187,0.8789063 h -1.359375 c 0,-0.3896485 0.140625,-0.7675781 0.421875,-1.1367188 0.28125,-0.375 0.65918,-0.6679687 1.136719,-0.8789062 0.483398,-0.2167969 1.013671,-0.328125 1.59375,-0.328125 0.914062,0 1.628906,0.2314453 2.144531,0.6914062 0.515625,0.4541016 0.785156,1.0839844 0.808594,1.8867188 v 3.6445312 c 0,0.7265625 0.08789,1.30664065 0.269531,1.73437503 V 6.2500004e-7 Z M 54.923828,-1.0312494 c 0.427734,0 0.832031,-0.1083984 1.207031,-0.328125 0.38086,-0.2167968 0.65918,-0.5039062 0.832032,-0.8554687 v -1.6289063 h -1.066407 c -1.658203,0 -2.484375,0.4863282 -2.484375,1.453125 0,0.4306641 0.140625,0.7675782 0.421875,1.0078125 0.28125,0.234375 0.644532,0.3515625 1.089844,0.3515625 z m 7.335938,-8.8125 v 1.921875 h 1.488281 v 1.0429688 h -1.488281 v 4.9101562 c 0,0.3222657 0.06445,0.5625 0.199218,0.7265625 0.131836,0.1582032 0.357422,0.234375 0.679688,0.234375 0.155273,0 0.36914,-0.029297 0.644531,-0.09375 V 6.2500004e-7 C 63.422852,0.09961 63.074219,0.15234438 62.740234,0.15234438 c -0.603515,0 -1.060547,-0.18164063 -1.371093,-0.55078125 -0.304688,-0.36621094 -0.457032,-0.89062503 -0.457032,-1.57031253 v -4.9101562 h -1.441406 v -1.0429688 h 1.441406 v -1.921875 z M 66.786133,6.2500004e-7 H 65.438477 V -7.9218744 h 1.347656 z M 65.321289,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199219,-0.550782 0.140625,-0.155273 0.339844,-0.234375 0.597656,-0.234375 0.263672,0 0.462891,0.0791 0.597656,0.234375 0.140625,0.149414 0.210938,0.333985 0.210938,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210938,0.5507809 -0.134765,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257812,0 -0.457031,-0.073242 -0.597656,-0.2226562 -0.134766,-0.1464844 -0.199219,-0.3310547 -0.199219,-0.5507809 z m 3.266602,5.9999996 c 0,-0.7792968 0.152343,-1.4794922 0.457031,-2.0976562 0.304687,-0.6240235 0.726562,-1.1044922 1.265625,-1.4414063 0.544922,-0.3339843 1.171875,-0.5039062 1.875,-0.5039062 1.078125,0 1.948242,0.375 2.613281,1.125 0.670899,0.7441406 1.007813,1.734375 1.007813,2.9765625 v 0.09375 c 0,0.7734375 -0.149414,1.4707031 -0.445313,2.0859375 -0.298828,0.609375 -0.723633,1.08691404 -1.277344,1.42968748 -0.547851,0.34570312 -1.177734,0.515625 -1.886718,0.515625 -1.072266,0 -1.942383,-0.375 -2.613282,-1.125 C 68.918945,-1.7226556 68.587891,-2.7099603 68.587891,-3.9374994 Z m 1.359375,0.1523438 c 0,0.8847656 0.202148,1.5908203 0.609375,2.1210937 0.413086,0.5332032 0.960937,0.79687503 1.640625,0.79687503 0.685546,0 1.233398,-0.26953123 1.640625,-0.80859373 0.404296,-0.5390625 0.609375,-1.2919922 0.609375,-2.2617188 0,-0.8730468 -0.208008,-1.5820312 -0.621094,-2.1210937 -0.416016,-0.5390625 -0.960938,-0.8085938 -1.640625,-0.8085938 -0.673828,0 -1.21582,0.2666016 -1.628906,0.796875 -0.407227,0.5332032 -0.609375,1.2949219 -0.609375,2.2851563 z m 8.830078,-4.0429688 0.04687,0.9960938 c 0.600586,-0.7646485 1.388672,-1.1484375 2.367187,-1.1484375 1.678711,0 2.522461,0.946289 2.53125,2.8359375 V 6.2500004e-7 H 82.375 V -5.2499994 c -0.0088,-0.5683593 -0.140625,-0.9902343 -0.398438,-1.265625 -0.251953,-0.2724609 -0.65039,-0.4101562 -1.195312,-0.4101562 -0.439453,0 -0.826172,0.1171875 -1.160156,0.3515625 -0.328125,0.234375 -0.585938,0.5449219 -0.773438,0.9257812 V 6.2500004e-7 H 77.5 V -7.9218744 Z M 94.357422,6.2500004e-7 C 94.27832,-0.15527281 94.216797,-0.43359312 94.169922,-0.83203062 c -0.632813,0.65625 -1.388672,0.984375 -2.261719,0.984375 -0.782226,0 -1.423828,-0.22265625 -1.921875,-0.66796875 -0.500976,-0.4453125 -0.75,-1.00781253 -0.75,-1.68750003 0,-0.8203125 0.310547,-1.4560547 0.9375,-1.9101562 0.632813,-0.459961 1.514649,-0.6914063 2.648438,-0.6914063 h 1.324218 v -0.6210937 c 0,-0.4746094 -0.146484,-0.8554688 -0.433593,-1.1367188 -0.28125,-0.28125 -0.697266,-0.421875 -1.242188,-0.421875 -0.486328,0 -0.890625,0.1259766 -1.21875,0.375 -0.328125,0.2431641 -0.492187,0.5361328 -0.492187,0.8789063 h -1.359375 c 0,-0.3896485 0.140625,-0.7675781 0.421875,-1.1367188 0.28125,-0.375 0.659179,-0.6679687 1.136718,-0.8789062 0.483399,-0.2167969 1.013672,-0.328125 1.59375,-0.328125 0.914063,0 1.628907,0.2314453 2.144532,0.6914062 0.515625,0.4541016 0.785156,1.0839844 0.808593,1.8867188 v 3.6445312 c 0,0.7265625 0.08789,1.30664065 0.269532,1.73437503 V 6.2500004e-7 Z M 92.107422,-1.0312494 c 0.427734,0 0.832031,-0.1083984 1.207031,-0.328125 0.380859,-0.2167968 0.65918,-0.5039062 0.832031,-0.8554687 v -1.6289063 h -1.066406 c -1.658203,0 -2.484375,0.4863282 -2.484375,1.453125 0,0.4306641 0.140625,0.7675782 0.421875,1.0078125 0.28125,0.234375 0.644531,0.3515625 1.089844,0.3515625 z m 6.785156,-6.890625 0.04687,0.9960938 c 0.600586,-0.7646485 1.388682,-1.1484375 2.367192,-1.1484375 1.6787,0 2.52245,0.946289 2.53125,2.8359375 V 6.2500004e-7 h -1.34767 V -5.2499994 c -0.009,-0.5683593 -0.14062,-0.9902343 -0.39843,-1.265625 -0.25196,-0.2724609 -0.65039,-0.4101562 -1.19532,-0.4101562 -0.43944,0 -0.82617,0.1171875 -1.160147,0.3515625 -0.328125,0.234375 -0.585937,0.5449219 -0.773437,0.9257812 V 6.2500004e-7 H 97.615234 V -7.9218744 Z m 6.647462,3.890625 c 0,-1.2099609 0.28711,-2.1855468 0.86719,-2.9296875 0.57715,-0.7412109 1.33007,-1.1132812 2.26172,-1.1132812 0.92871,0 1.66406,0.3164062 2.20312,0.9492187 v -4.1249996 h 1.35938 V 6.2500004e-7 h -1.24219 L 110.91895,-0.85546812 c -0.53907,0.67382812 -1.29493,1.0078125 -2.26172,1.0078125 -0.91407,0 -1.66407,-0.375 -2.25,-1.125 C 105.82715,-1.728515 105.54004,-2.71289 105.54004,-3.9257806 Z m 1.35937,0.1523438 c 0,0.899414 0.18164,1.602539 0.55079,2.109375 0.375,0.5097656 0.89062,0.7617187 1.54687,0.7617187 0.8584,0 1.48242,-0.3808593 1.875,-1.1484375 v -3.6445312 c -0.39844,-0.75 -1.01953,-1.125 -1.86328,-1.125 -0.66504,0 -1.18359,0.2578125 -1.55859,0.7734375 -0.36915,0.515625 -0.55079,1.274414 -0.55079,2.2734375 z m 0,0"
       style="fill:#484848;fill-opacity:1;fill-rule:nonzero;stroke:none"
       aria-label="Organization and"
       transform="matrix(1.3333333,0,0,1.3333333,732.04167,476.49219)"
       clip-path="url(#clipPath33)" />
    <path
       id="path34"
       d="M 5.1455078,-4.3124994 H 2.6494141 V 6.2499998e-7 H 1.2314453 V -10.664062 h 3.5273438 c 1.2011718,0 2.1269531,0.275391 2.7773437,0.8203126 0.647461,0.5478516 0.9726563,1.3447266 0.9726563,2.390625 0,0.6650391 -0.1816407,1.2421875 -0.5390625,1.734375 -0.3603516,0.4921875 -0.8613282,0.8613281 -1.5,1.1015625 l 2.5078125,4.52343752 V 6.25e-7 H 7.4658203 Z M 2.6494141,-5.4609369 h 2.15625 c 0.6943359,0 1.2480468,-0.1787109 1.6640625,-0.5390625 0.4130859,-0.3662109 0.6210937,-0.8496094 0.6210937,-1.453125 0,-0.6621094 -0.1992187,-1.171875 -0.5976562,-1.5234375 C 6.1005859,-9.3281244 5.5351562,-9.5039056 4.7939453,-9.5039056 H 2.6494141 Z M 13.536133,0.15234437 c -1.072266,0 -1.945313,-0.3515625 -2.625,-1.0546875 C 10.237305,-1.6113275 9.9033203,-2.5576166 9.9033203,-3.7382806 v -0.2578125 c 0,-0.7792969 0.1464847,-1.4794922 0.4453127,-2.0976563 0.304687,-0.6152344 0.726562,-1.1015625 1.265625,-1.453125 0.539062,-0.3515625 1.125,-0.5273437 1.757812,-0.5273437 1.03125,0 1.831055,0.3398437 2.402344,1.0195312 0.568359,0.6796875 0.855469,1.6523438 0.855469,2.9179688 v 0.5625 h -5.367188 c 0.01465,0.7822265 0.240235,1.415039 0.679688,1.8984375 0.436523,0.477539 0.990234,0.71484372 1.664062,0.71484372 0.483399,0 0.890625,-0.0966797 1.21875,-0.29296872 0.333985,-0.1933594 0.626953,-0.4511719 0.878907,-0.7734375 l 0.820312,0.6445312 c -0.665039,1.02539065 -1.661133,1.53515627 -2.988281,1.53515627 z M 13.37207,-6.9609369 c -0.547851,0 -1.007812,0.1992188 -1.382812,0.5976563 -0.369141,0.3984375 -0.594727,0.9580078 -0.679688,1.6757812 h 3.960938 v -0.1054687 c -0.04102,-0.6855469 -0.228516,-1.21875 -0.5625,-1.59375 -0.328125,-0.3808594 -0.773438,-0.5742188 -1.335938,-0.5742188 z m 11.510742,3.0820313 c 0,1.2128906 -0.27832,2.1884765 -0.832031,2.92968747 -0.547851,0.73535157 -1.294922,1.1015625 -2.238281,1.1015625 -0.960938,0 -1.719727,-0.30761718 -2.273438,-0.92578125 V 3.0468756 h -1.347656 v -10.96875 h 1.230469 l 0.07031,0.8789063 c 0.544922,-0.6855469 1.3125,-1.03125 2.296875,-1.03125 0.952149,0 1.705079,0.3603515 2.261719,1.078125 0.553711,0.7207031 0.832031,1.7197265 0.832031,3 z m -1.359375,-0.1523438 c 0,-0.890625 -0.193359,-1.59375 -0.574218,-2.109375 -0.375,-0.5214844 -0.896485,-0.7851562 -1.558594,-0.7851562 -0.820313,0 -1.438477,0.3632812 -1.851563,1.0898437 v 3.796875 c 0.404297,0.7207031 1.025391,1.07812502 1.863282,1.07812502 0.647461,0 1.163086,-0.25781252 1.546875,-0.77343752 0.380859,-0.515625 0.574218,-1.2802734 0.574218,-2.296875 z m 6.902344,-2.6835937 c -0.205078,-0.029297 -0.421875,-0.046875 -0.65625,-0.046875 -0.890625,0 -1.49707,0.3808593 -1.816406,1.1367187 V 6.2499998e-7 H 26.605469 V -7.9218744 h 1.3125 l 0.02344,0.9140625 c 0.445313,-0.7089844 1.072266,-1.0664062 1.886719,-1.0664062 0.263672,0 0.462891,0.035156 0.597656,0.1054687 z m 0.887696,2.6835937 c 0,-0.7792969 0.152343,-1.4794922 0.457031,-2.0976562 0.304687,-0.6240235 0.726562,-1.1044922 1.265625,-1.4414063 0.544922,-0.3339844 1.171875,-0.5039062 1.875,-0.5039062 1.078125,0 1.948242,0.375 2.613281,1.125 0.670898,0.7441406 1.007813,1.734375 1.007813,2.9765625 v 0.09375 c 0,0.7734375 -0.149415,1.4707031 -0.445313,2.0859375 -0.298828,0.609375 -0.723633,1.08691404 -1.277344,1.42968747 -0.547851,0.34570313 -1.177734,0.515625 -1.886718,0.515625 -1.072266,0 -1.942383,-0.375 -2.613282,-1.125 C 31.644531,-1.7226556 31.313477,-2.7099603 31.313477,-3.9374994 Z m 1.359375,0.1523438 c 0,0.8847656 0.202148,1.5908203 0.609375,2.1210937 0.413085,0.5332031 0.960937,0.79687502 1.640625,0.79687502 0.685546,0 1.233398,-0.26953122 1.640625,-0.80859372 0.404296,-0.5390625 0.609375,-1.2919922 0.609375,-2.2617188 0,-0.8730469 -0.208008,-1.5820312 -0.621094,-2.1210937 -0.416016,-0.5390625 -0.960938,-0.8085938 -1.640625,-0.8085938 -0.673828,0 -1.215821,0.2666016 -1.628906,0.796875 -0.407227,0.5332031 -0.609375,1.2949219 -0.609375,2.2851563 z m 7.21289,-0.1523438 c 0,-1.2099609 0.28711,-2.1855469 0.867188,-2.9296875 0.577148,-0.7412109 1.330078,-1.1132812 2.261718,-1.1132812 0.928711,0 1.664063,0.3164062 2.203125,0.9492187 v -4.1249996 h 1.359375 V 6.2499998e-7 H 45.334961 L 45.264648,-0.85546813 c -0.539062,0.67382813 -1.294921,1.0078125 -2.261718,1.0078125 -0.914063,0 -1.664063,-0.375 -2.25,-1.125 C 40.172852,-1.728515 39.885742,-2.71289 39.885742,-3.9257806 Z m 1.359375,0.1523438 c 0,0.899414 0.181641,1.602539 0.550781,2.109375 0.375,0.5097656 0.890625,0.7617187 1.546875,0.7617187 0.858399,0 1.482422,-0.3808594 1.875,-1.1484375 v -3.6445312 c -0.398437,-0.75 -1.019531,-1.125 -1.863281,-1.125 -0.665039,0 -1.183594,0.2578125 -1.558594,0.7734375 -0.36914,0.515625 -0.550781,1.274414 -0.550781,2.2734375 z m 12.313477,3.09374997 c -0.524414,0.62695313 -1.297852,0.9375 -2.320313,0.9375 -0.84375,0 -1.488281,-0.24609375 -1.933594,-0.73828125 C 48.865234,-1.0781244 48.642578,-1.8046869 48.636719,-2.7656244 v -5.15625 h 1.359375 v 5.1210938 c 0,1.1953125 0.486328,1.7929687 1.464843,1.7929687 1.03125,0 1.716797,-0.3808594 2.0625,-1.1484375 v -5.765625 h 1.359375 V 6.2499998e-7 H 53.59375 Z m 6.553711,-0.17578125 c 0.483398,0 0.905273,-0.14355472 1.265625,-0.43359372 0.357422,-0.2958985 0.55664,-0.6621094 0.597656,-1.1015625 h 1.289062 c -0.03223,0.4541015 -0.193359,0.8876953 -0.480468,1.3007812 -0.28125,0.40722659 -0.665039,0.73535159 -1.148438,0.98437502 -0.477539,0.24023438 -0.984375,0.36328125 -1.523437,0.36328125 -1.078125,0 -1.939453,-0.35742187 -2.578125,-1.078125 C 56.901367,-1.6523431 56.584961,-2.6396478 56.584961,-3.8906244 v -0.2226562 c 0,-0.7734375 0.140625,-1.4589844 0.421875,-2.0625 0.28125,-0.600586 0.685547,-1.0664063 1.21875,-1.3945313 0.530273,-0.3339844 1.154297,-0.5039062 1.875,-0.5039062 0.890625,0 1.628906,0.2666015 2.214844,0.796875 0.591797,0.5332031 0.908203,1.2246093 0.949218,2.0742187 h -1.289062 c -0.04102,-0.5068359 -0.234375,-0.9257812 -0.585938,-1.2539062 -0.345703,-0.3339844 -0.773437,-0.5039063 -1.289062,-0.5039063 -0.688477,0 -1.224609,0.2519531 -1.605469,0.75 -0.375,0.4921875 -0.5625,1.2070313 -0.5625,2.1445313 v 0.2578125 c 0,0.9140625 0.1875,1.6171875 0.5625,2.109375 0.375,0.4921875 0.914063,0.73828122 1.617188,0.73828122 z m 6.498047,-8.88281252 v 1.921875 h 1.488281 v 1.0429688 h -1.488281 v 4.9101562 c 0,0.3222656 0.06445,0.5625 0.199218,0.7265625 0.131836,0.1582031 0.357422,0.234375 0.679688,0.234375 0.155273,0 0.36914,-0.029297 0.644531,-0.09375 V 6.2499998e-7 C 67.773437,0.09961 67.424805,0.15234437 67.09082,0.15234437 c -0.603515,0 -1.060547,-0.18164062 -1.371093,-0.55078125 -0.304688,-0.36621093 -0.457032,-0.89062502 -0.457032,-1.57031252 v -4.9101562 h -1.441406 v -1.0429688 h 1.441406 v -1.921875 z M 71.136719,6.2499998e-7 H 69.789062 V -7.9218744 h 1.347657 z M 69.671875,-10.031249 c 0,-0.216797 0.06445,-0.401368 0.199219,-0.550782 0.140625,-0.155273 0.339843,-0.234375 0.597656,-0.234375 0.263672,0 0.462891,0.0791 0.597656,0.234375 0.140625,0.149414 0.210938,0.333985 0.210938,0.550782 0,0.2197262 -0.07031,0.4042965 -0.210938,0.5507809 -0.134765,0.149414 -0.333984,0.2226562 -0.597656,0.2226562 -0.257813,0 -0.457031,-0.073242 -0.597656,-0.2226562 -0.134766,-0.1464844 -0.199219,-0.3310547 -0.199219,-0.5507809 z m 3.266602,5.9999996 c 0,-0.7792969 0.152343,-1.4794922 0.457031,-2.0976562 0.304687,-0.6240235 0.726562,-1.1044922 1.265625,-1.4414063 0.544922,-0.3339844 1.171875,-0.5039062 1.875,-0.5039062 1.078125,0 1.948242,0.375 2.613281,1.125 0.670898,0.7441406 1.007813,1.734375 1.007813,2.9765625 v 0.09375 c 0,0.7734375 -0.149415,1.4707031 -0.445313,2.0859375 -0.298828,0.609375 -0.723633,1.08691404 -1.277344,1.42968747 -0.547851,0.34570313 -1.177734,0.515625 -1.886718,0.515625 -1.072266,0 -1.942383,-0.375 -2.613282,-1.125 C 73.269531,-1.7226556 72.938477,-2.7099603 72.938477,-3.9374994 Z m 1.359375,0.1523438 c 0,0.8847656 0.202148,1.5908203 0.609375,2.1210937 0.413085,0.5332031 0.960937,0.79687502 1.640625,0.79687502 0.685546,0 1.233398,-0.26953122 1.640625,-0.80859372 0.404296,-0.5390625 0.609375,-1.2919922 0.609375,-2.2617188 0,-0.8730469 -0.208008,-1.5820312 -0.621094,-2.1210937 -0.416016,-0.5390625 -0.960938,-0.8085938 -1.640625,-0.8085938 -0.673828,0 -1.215821,0.2666016 -1.628906,0.796875 C 74.5,-5.6308588 74.297852,-4.86914 74.297852,-3.8789056 Z m 8.830078,-4.0429688 0.04687,0.9960938 c 0.600586,-0.7646485 1.388672,-1.1484375 2.367187,-1.1484375 1.678711,0 2.522461,0.946289 2.53125,2.8359375 V 6.2499998e-7 H 86.725586 V -5.2499994 c -0.0088,-0.5683594 -0.140625,-0.9902344 -0.398438,-1.265625 -0.251953,-0.2724609 -0.65039,-0.4101562 -1.195312,-0.4101562 -0.439453,0 -0.826172,0.1171875 -1.160156,0.3515625 -0.328125,0.234375 -0.585938,0.5449218 -0.773438,0.9257812 V 6.2499998e-7 H 81.850586 V -7.9218744 Z m 0,0"
       style="fill:#484848;fill-opacity:1;fill-rule:nonzero;stroke:none"
       aria-label="Reproduction"
       transform="matrix(1.3333333,0,0,1.3333333,732.04167,500.49219)"
       clip-path="url(#clipPath35)" />
    <path
       id="path36"
       d="M 268.1439,181 C 251.5099,234.8634 201.3254,274 142,274 69.0984,274 10,214.9016 10,142 10,69.0984 69.0984,10 142,10 c 59.3254,0 109.5099,39.1366 126.1439,93 H 255.5202 C 239.3324,55.8707 194.6217,22 142,22 75.7258,22 22,75.7258 22,142 c 0,66.2742 53.7258,120 120,120 52.6217,0 97.3324,-33.8707 113.5202,-81 z"
       style="fill:#4a386b;fill-opacity:1;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,44.04167,124.04167)"
       clip-path="url(#clipPath37)" />
    <path
       id="path38"
       d="M 461.0794,10 H 178.2829 L 71.7831,76 H 10 c 0.4918,3.9438 0.7922,7.947 0.8916,12 h 437.196 V 71.9389 l 29.453,-24.8673 v -5.2132 h -30.6134 v -6.4779 c 0,-6.1018 1.6196,-11.71 4.9715,-16.6092 2.4282,-3.5492 5.5163,-6.4673 9.1807,-8.7713 z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,378.80436,192.04167)"
       clip-path="url(#clipPath39)" />
    <path
       id="path40"
       d="M 454.08813,88 V 74.7257 l 28.2371,-23.8407 c 3.3524,-2.8319 5.8758,-5.1859 7.5704,-7.062 1.6946,-1.9115 2.8366,-3.6106 3.426,-5.0973 0.6263,-1.4868 0.9394,-3.0089 0.9394,-4.5664 v -0.1062 c 0,-1.8407 -0.4605,-3.4513 -1.3815,-4.8319 -0.8841,-1.4159 -2.1182,-2.5132 -3.7022,-3.292 -1.5841,-0.8142 -3.4261,-1.2212 -5.5259,-1.2212 -2.3945,0 -4.4943,0.4601 -6.2994,1.3805 -1.7683,0.8849 -3.1498,2.1239 -4.1445,3.7168 -0.9946,1.5929 -1.5472,3.4159 -1.6577,5.469 l -0.0553,0.5841 h -18.5668 v -0.4779 c 0,-4.9911 1.3078,-9.3982 3.9233,-13.2212 2.6156,-3.823 6.2259,-6.7965 10.8307,-8.9204 4.6417,-2.1593 9.9465,-3.2389 15.9145,-3.2389 6.0784,0 11.3832,0.9735 15.9144,2.9204 4.5312,1.9115 8.0493,4.584 10.5544,8.0176 2.5419,3.3983 3.8128,7.3806 3.8128,11.947 v 0.1061 c 0,3.2567 -0.5894,6.2124 -1.7683,8.8673 -1.1788,2.6195 -3.0945,5.3274 -5.7469,8.1239 -2.6524,2.7611 -6.1889,5.9823 -10.6096,9.6637 l -16.2508,13.3274 h 35.4255 V 88 Z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,378.80436,192.04167)"
       clip-path="url(#clipPath41)" />
    <path
       id="path42"
       d="M 10.8916,10 C 10.7922,14.053 10.4918,18.0562 10,22 h 61.7865 l 106.0002,66 h 281.9065 c -3.0894,-1.9458 -5.7651,-4.3362 -7.9631,-7.1953 -3.3604,-4.3713 -5.2528,-9.4444 -5.7288,-15.0444 l -0.002,-0.0229 -0.5535,-7.1635 h 21.6548 V 38.9565 h -19.8373 l 0.515,-7.178 10e-4,-0.0182 c 0.4279,-5.4945 2.17,-10.4868 5.3431,-14.7787 2.0265,-2.7636 4.4967,-5.0855 7.3549,-6.9816 z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,378.80436,304.04167)"
       clip-path="url(#clipPath43)" />
    <path
       id="path44"
       d="m 482.79673,88 c -5.9747,0 -11.1981,-0.9565 -15.6703,-2.8696 -4.4723,-1.913 -8.0187,-4.5739 -10.6391,-7.9826 -2.6205,-3.4087 -4.1228,-7.3739 -4.5072,-11.8956 l -0.0524,-0.6783 h 18.3432 l 0.1048,0.6261 c 0.3145,2.1217 1.5548,3.9478 3.7211,5.4783 2.2012,1.4956 5.1011,2.2434 8.6999,2.2434 2.3758,0 4.4198,-0.3826 6.1319,-1.1478 1.7469,-0.7652 3.0921,-1.8087 4.0355,-3.1304 0.9433,-1.3565 1.415,-2.9044 1.415,-4.6435 v -0.1044 c 0,-3.0608 -1.1355,-5.3913 -3.4066,-6.9913 -2.2711,-1.6 -5.5029,-2.4 -9.6957,-2.4 h -8.1758 V 41.513 h 8.071 c 2.4807,0 4.5945,-0.3652 6.3415,-1.0956 1.7819,-0.7304 3.1445,-1.7565 4.0879,-3.0783 0.9783,-1.3217 1.4675,-2.8522 1.4675,-4.5913 v -0.1043 c 0,-1.7392 -0.4193,-3.2348 -1.2578,-4.487 -0.8036,-1.2521 -1.9916,-2.2087 -3.5639,-2.8695 -1.5373,-0.6609 -3.3891,-0.9913 -5.5553,-0.9913 -2.2012,0 -4.1404,0.3478 -5.8175,1.0434 -1.6421,0.6609 -2.9523,1.6174 -3.9306,2.8696 -0.9434,1.2174 -1.5199,2.6435 -1.7295,4.2783 l -0.0525,0.4695 h -17.4522 l 0.0524,-0.7304 c 0.3494,-4.487 1.747,-8.3826 4.1927,-11.687 2.4458,-3.3391 5.7651,-5.9304 9.9578,-7.7739 4.2277,-1.8435 9.1541,-2.7652 14.7794,-2.7652 5.73,0 10.7089,0.8348 14.9365,2.5043 4.2627,1.6348 7.5469,3.9479 9.8529,6.9392 2.3061,2.9913 3.4591,6.5043 3.4591,10.5391 v 0.1044 c 0,3.1652 -0.7163,5.9304 -2.1488,8.2956 -1.3976,2.3304 -3.2843,4.2435 -5.6602,5.7391 -2.3758,1.4957 -4.9788,2.5392 -7.8089,3.1305 v 0.3652 c 5.6602,0.5565 10.1673,2.3478 13.5215,5.3739 3.3891,3.0261 5.0837,7.0261 5.0837,12 v 0.1044 c 0,4.626 -1.2753,8.6608 -3.8259,12.1043 -2.5505,3.4087 -6.1493,6.0696 -10.7962,7.9826 -4.647,1.8783 -10.15,2.8174 -16.5089,2.8174 z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,378.80436,304.04167)"
       clip-path="url(#clipPath45)" />
    <path
       id="path46"
       d="M 476.3098,76 H 179.8815 L 73.8813,10 H 12.9072 C 12.1574,14.248 11.1841,18.4188 10,22.5 h 60.1197 l 112.0022,131.0023 304.0165,0.4764 v -7.276 h -38.4011 v -23.8189 l 0.8501,-1.422 c 1.9523,-3.2657 3.9228,-6.5133 5.9114,-9.7428 l 0.005,-0.008 0.005,-0.008 c 2.0023,-3.2296 3.9866,-6.4592 5.953,-9.6886 l 5.9245,-9.7297 c 1.9773,-3.2474 3.9547,-6.4769 5.9322,-9.6884 1.3389,-2.1989 2.6695,-4.3978 3.9917,-6.5966 z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,373.72567,328.04167)"
       clip-path="url(#clipPath47)" />
    <path
       id="path48"
       d="m 459.60791,114.8649 c -1.9748,3.2072 -3.93171,6.4324 -5.87061,9.6756 v 16.1622 h 38.4011 V 154 h 18.74281 v -13.2973 h 7.85609 v -15.4594 h -7.85609 V 76 H 483.3057 c -1.9389,3.2432 -3.8958,6.4865 -5.87059,9.7297 -1.97491,3.2072 -3.9497,6.4325 -5.92451,9.6757 l -5.92439,9.7297 c -1.97481,3.2433 -3.9676,6.4865 -5.9783,9.7298 z m 10.66359,11.0811 h 22.4051 V 89.6758 h -0.43079 l -4.4164,7.1351 c -1.4362,2.3784 -2.8904,4.7568 -4.36251,7.1351 -1.4363,2.3784 -2.9085,4.7748 -4.41649,7.1892 l -4.4164,7.1352 c -1.4362,2.3783 -2.8904,4.7567 -4.36251,7.1351 z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,373.72567,328.04167)"
       clip-path="url(#clipPath49)" />
    <path
       id="path50"
       d="M 476.5765,10 H 183.9683 L 69.9681,142 H 10 c 1.1193,3.9217 2.0441,7.9254 2.7633,12 H 73.7408 L 180.2407,88 H 481.1732 V 38.5068 L 461.5934,51.8233 V 20.3691 Z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,373.91635,80.04167)"
       clip-path="url(#clipPath51)" />
    <path
       id="path52"
       d="M 487.17355,88 V 27.4595 h -0.4256 l -19.1542,13.027 V 23.5135 L 487.12035,10 h 19.4734 v 78 z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,373.91635,80.04167)"
       clip-path="url(#clipPath53)" />
    <path
       id="path54"
       d="M 31,57 H 13 c -1.10457,0 -2,-0.89543 -2,-2 V 13 c 0,-1.10457 0.89543,-2 2,-2 h 26.586 c 0.53068,6.4e-4 1.03934,0.21217 1.414,0.588 L 48.414,19 c 0.3751,0.37498 0.58589,0.88361 0.586,1.414 V 27 M 27.962,40.948 c -5.09654,-0.53602 -8.96302,-4.83809 -8.95401,-9.96273 0.009,-5.12464 3.8906,-9.41308 8.98899,-9.93118 5.09839,-0.5181 9.7633,2.90184 10.80302,7.91991 M 29,25.002 v 6 h 4 m 0,14 c 0,6.62742 5.37258,12 12,12 6.62742,0 12,-5.37258 12,-12 0,-6.62742 -5.37258,-12 -12,-12 -6.62742,0 -12,5.37258 -12,12 z m 8.25,-2.918 c 0,-2.07107 1.67893,-3.75 3.75,-3.75 2.07107,0 3.75,1.67893 3.75,3.75 0,2.07107 -1.67893,3.75 -3.75,3.75 v 2 m 0,4 c 0.27614,0 0.5,0.22386 0.5,0.5 0,0.27614 -0.22386,0.5 -0.5,0.5 -0.27614,0 -0.5,-0.22386 -0.5,-0.5 0,-0.27614 0.22386,-0.5 0.5,-0.5"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,636.04167,100.04167)"
       clip-path="url(#clipPath55)" />
    <path
       id="path56"
       d="M 53,11 H 19 c -2.20914,0 -4,1.79086 -4,4 0,2.20914 1.79086,4 4,4 h 32 c 1.10457,0 2,0.89543 2,2 v 34 c 0,1.10457 -0.89543,2 -2,2 H 19 c -2.20914,0 -4,-1.79086 -4,-4 V 15 m 4,0 h 32 m -4,15 c 0,-1.65686 -1.34314,-3 -3,-3 H 26 c -1.65685,0 -3,1.34314 -3,3 v 18 c 0,1.65686 1.34315,3 3,3 h 18 c 1.65686,0 3,-1.34314 3,-3 z m -16,9 v -3.64 c -10e-5,-0.30979 0.16642,-0.59569 0.43592,-0.74845 0.26951,-0.15276 0.60034,-0.14877 0.86608,0.01045 l 6.068,3.64 c 0.25956,0.15529 0.41846,0.43552 0.41846,0.738 0,0.30247 -0.1589,0.5827 -0.41846,0.738 l -6.068,3.64 c -0.26574,0.15922 -0.59657,0.16321 -0.86608,0.01045 C 31.16642,43.23569 30.9999,42.94979 31,42.64 Z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,636.04167,212.04167)"
       clip-path="url(#clipPath57)" />
    <path
       id="path58"
       d="m 25.72352,25.39994 0.59996,-3.6 c 0,0 3.00002,-3 6.19992,0 3.2,3 0,6.2 0,6.2 l -3.19992,0.8 m 3.19992,-0.8 c 0,0 3,-1.6 3.8,2.40006 0.6,2.6 -0.6,2.4 -10.99992,5.4 m 1.00464,-14.00006 c 0,0 1.60002,-3 -2.39998,-3.8 -2.8,-0.6 -2.4046,1.4 -4.8046,11.2 m 6.40002,6.40006 -1,1 c -1.8,1.8 -4.6,1.8 -6.4,0 -1.8,-1.8 -1.8,-4.6 0,-6.4 l 1,-1.00004 z M 47.5,44.5 c -3.3138,0 -6,-2.6862 -6,-6 0,-3.3138 2.6862,-6 6,-6 3.3138,0 6,2.6862 6,6 0,3.3138 -2.6862,6 -6,6 z m -9,12 c 0,-5 4,-9 9,-9 5,0 9,4 9,9 M 52.7,26.3 v -12 c 0,-1.6 -1.2,-2.8 -2.8,-2.8 H 14.30008 c -1.6,0 -2.79999,1.2 -2.79999,2.8 v 27.4 c 0,1.6 1.19999,2.8 2.79999,2.8 H 34.5 m -7.19996,0 -1.39998,8 m 6.79994,0 h -8.79992"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,636.04167,324.04167)"
       clip-path="url(#clipPath59)" />
    <path
       id="path60"
       d="m 46.5,11.5 h -25 C 20.67158,11.5 20,12.17158 20,13 v 10 c 0,0.82842 0.67158,1.5 1.5,1.5 h 25 C 47.3284,24.5 48,23.82842 48,23 V 13 c 0,-0.82842 -0.6716,-1.5 -1.5,-1.5 z M 34,24.5 v 23 m -18,0 v -8 c 0,-0.7956 0.31608,-1.5588 0.87868,-2.1214 C 17.44128,36.816 18.20436,36.5 19,36.5 h 30 c 0.7956,0 1.5588,0.316 2.1214,0.8786 C 51.684,37.9412 52,38.7044 52,39.5 v 8 m -36,9 c 2.48528,0 4.5,-2.0148 4.5,-4.5 0,-2.4852 -2.01472,-4.5 -4.5,-4.5 -2.48528,0 -4.5,2.0148 -4.5,4.5 0,2.4852 2.01472,4.5 4.5,4.5 z m 18,0 c 2.4852,0 4.5,-2.0148 4.5,-4.5 0,-2.4852 -2.0148,-4.5 -4.5,-4.5 -2.4852,0 -4.5,2.0148 -4.5,4.5 0,2.4852 2.0148,4.5 4.5,4.5 z m 18,0 c 2.4852,0 4.5,-2.0148 4.5,-4.5 0,-2.4852 -2.0148,-4.5 -4.5,-4.5 -2.4852,0 -4.5,2.0148 -4.5,4.5 0,2.4852 2.0148,4.5 4.5,4.5 z"
       style="fill:none;stroke:#484848;stroke-width:1;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-opacity:1"
       transform="matrix(1.3333333,0,0,1.3333333,636.04167,436.04167)"
       clip-path="url(#clipPath61)" />
  </g>
</svg>

************************

          {{1}}
************************

<svg
   width="1000"
   height="330"
   xml:space="preserve"
   overflow="hidden"
   version="1.1"
   id="svg47"
   viewBox="0 0 249.99863 82.134"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:svg="http://www.w3.org/2000/svg"><defs
     id="defs47" /><g
     transform="matrix(0.06354873,0,0,0.05806225,-14.875109,-31.49779)"
     id="g47"><g
       id="g46"><path
         d="M 315.682,650.283 H 1268.4 V 793.272 H 315.682 Z"
         fill="#dfde97"
         fill-rule="evenodd"
         fill-opacity="0.639216"
         id="path1" /><path
         d="m 1268.4,650.283 h 797.56 V 793.272 H 1268.4 Z"
         fill="#dfde97"
         fill-rule="evenodd"
         fill-opacity="0.639216"
         id="path2" /><path
         d="M 2065.96,650.283 H 3173.84 V 793.272 H 2065.96 Z"
         fill="#dfde97"
         fill-rule="evenodd"
         fill-opacity="0.639216"
         id="path3" /><path
         d="m 3173.84,650.283 h 952.72 v 142.989 h -952.72 z"
         fill="#dfde97"
         fill-rule="evenodd"
         fill-opacity="0.639216"
         id="path4" /><path
         d="M 315.682,1013.26 H 1268.4 v 219.99 H 315.682 Z"
         fill="#fbdec8"
         fill-rule="evenodd"
         fill-opacity="0.501961"
         id="path5" /><path
         d="m 1268.4,1013.26 h 797.56 v 219.99 H 1268.4 Z"
         fill="#fbdec8"
         fill-rule="evenodd"
         fill-opacity="0.501961"
         id="path6" /><path
         d="m 2065.96,1013.26 h 1107.88 v 219.99 H 2065.96 Z"
         fill="#fbdec8"
         fill-rule="evenodd"
         fill-opacity="0.501961"
         id="path7" /><path
         d="m 3173.84,1013.26 h 952.72 v 219.99 h -952.72 z"
         fill="#fbdec8"
         fill-rule="evenodd"
         fill-opacity="0.501961"
         id="path8" /><path
         d="M 315.682,1453.24 H 1268.4 v 219.99 H 315.682 Z"
         fill="#fbdec8"
         fill-rule="evenodd"
         fill-opacity="0.501961"
         id="path9" /><path
         d="m 1268.4,1453.24 h 797.56 v 219.99 H 1268.4 Z"
         fill="#fbdec8"
         fill-rule="evenodd"
         fill-opacity="0.501961"
         id="path10" /><path
         d="m 2065.96,1453.24 h 1107.88 v 219.99 H 2065.96 Z"
         fill="#fbdec8"
         fill-rule="evenodd"
         fill-opacity="0.501961"
         id="path11" /><path
         d="m 3173.84,1453.24 h 952.72 v 219.99 h -952.72 z"
         fill="#fbdec8"
         fill-rule="evenodd"
         fill-opacity="0.501961"
         id="path12" /><path
         d="M 1268.4,648.564 V 1894.94"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path13" /><path
         d="M 2065.96,648.564 V 1894.94"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path14" /><path
         d="M 3173.84,648.564 V 1894.94"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path15" /><path
         d="M 313.963,793.272 H 4128.28"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path16" /><path
         d="M 313.963,1013.26 H 4128.28"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path17" /><path
         d="M 313.963,1233.25 H 4128.28"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path18" /><path
         d="M 313.963,1453.24 H 4128.28"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path19" /><path
         d="M 313.963,1673.23 H 4128.28"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path20" /><path
         d="M 315.682,648.564 V 1894.94"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path21" /><path
         d="M 4126.56,648.564 V 1894.94"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path22" /><path
         d="M 313.963,650.283 H 4128.28"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path23" /><path
         d="M 313.963,1893.22 H 4128.28"
         stroke="#9e9e9e"
         stroke-width="3.4375"
         stroke-linecap="butt"
         stroke-linejoin="round"
         stroke-miterlimit="10"
         stroke-opacity="1"
         fill="none"
         fill-rule="evenodd"
         id="path24" /><g
         id="g24"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(3206.84,745)"
           id="text24"
           style="text-decoration:none;text-decoration-line:none">LOs</text></g><g
         id="g25"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,745)"
           id="text25"
           style="text-decoration:none;text-decoration-line:none">Description</text></g><g
         id="g26"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(1301.4,745)"
           id="text26"
           style="text-decoration:none;text-decoration-line:none">Activity (LEs)</text></g><g
         id="g27"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(348.676,745)"
           id="text27"
           style="text-decoration:none;text-decoration-line:none">Time</text></g><g
         id="g28"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,888)"
           id="text28"
           style="text-decoration:none;text-decoration-line:none">Tour of the table for everyone </text></g><g
         id="g29"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,965)"
           id="text29"
           style="text-decoration:none;text-decoration-line:none">introduction</text></g><g
         id="g30"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(1301.4,888)"
           id="text30"
           style="text-decoration:none;text-decoration-line:none">Introduction</text></g><g
         id="g31"><text
           fill="#00205f"
           fill-opacity="1"
           font-family="'Apple Color Emoji', 'Apple Color Emoji_MSFontService', sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="83px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(348.676,903)"
           id="text31"
           style="text-decoration:none;text-decoration-line:none">⏰</text></g><g
         id="g32"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,1108)"
           id="text32"
           style="text-decoration:none;text-decoration-line:none">Each person should share what Tea </text></g><g
         id="g33"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,1185)"
           id="text33"
           style="text-decoration:none;text-decoration-line:none">they would be and why</text></g><g
         id="g34"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(1301.4,1108)"
           id="text34"
           style="text-decoration:none;text-decoration-line:none">Ice breaker</text></g><g
         id="g35"><text
           fill="#00205f"
           fill-opacity="1"
           font-family="'Apple Color Emoji', 'Apple Color Emoji_MSFontService', sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="83px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(348.676,1123)"
           id="text35"
           style="text-decoration:none;text-decoration-line:none">⏰</text></g><g
         id="g36"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,1328)"
           id="text36"
           style="text-decoration:none;text-decoration-line:none">Explaining the concept of ….</text></g><g
         id="g37"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(1301.4,1328)"
           id="text37"
           style="text-decoration:none;text-decoration-line:none">Lecture</text></g><g
         id="g38"><text
           fill="#00205f"
           fill-opacity="1"
           font-family="'Apple Color Emoji', 'Apple Color Emoji_MSFontService', sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="83px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(348.676,1343)"
           id="text38"
           style="text-decoration:none;text-decoration-line:none">⏰</text></g><g
         id="g39"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,1548)"
           id="text39"
           style="text-decoration:none;text-decoration-line:none">In groups of 3 they will ….</text></g><g
         id="g40"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(1301.4,1548)"
           id="text40"
           style="text-decoration:none;text-decoration-line:none">Group work</text></g><g
         id="g41"><text
           fill="#00205f"
           fill-opacity="1"
           font-family="'Apple Color Emoji', 'Apple Color Emoji_MSFontService', sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="83px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(348.676,1563)"
           id="text41"
           style="text-decoration:none;text-decoration-line:none">⏰</text></g><g
         id="g42"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,1768)"
           id="text42"
           style="text-decoration:none;text-decoration-line:none">Each group will share their thought </text></g><g
         id="g43"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(2098.95,1845)"
           id="text43"
           style="text-decoration:none;text-decoration-line:none">and …</text></g><g
         id="g44"><text
           fill="#000000"
           fill-opacity="1"
           font-family="Arial, Arial_MSFontService, sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="64px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(1301.4,1768)"
           id="text44"
           style="text-decoration:none;text-decoration-line:none">Group discussion</text></g><g
         id="g45"><text
           fill="#00205f"
           fill-opacity="1"
           font-family="'Apple Color Emoji', 'Apple Color Emoji_MSFontService', sans-serif"
           font-style="normal"
           font-variant="normal"
           font-weight="400"
           font-stretch="normal"
           font-size="83px"
           text-anchor="start"
           direction="ltr"
           writing-mode="lr-tb"
           unicode-bidi="normal"
           text-decoration="none"
           transform="translate(348.676,1783)"
           id="text45"
           style="text-decoration:none;text-decoration-line:none">⏰</text></g></g></g></svg>

*************************

## Create and explore Interoperable and Reproducible training material (text, presentation)

          --{{0}}--
Let's first have a look at example presentations using Liascript, a markdown dialect.

            {{0-1}}
*********************

**Example presentation**

[Rendering](https://liascript.github.io/course/?https://raw.githubusercontent.com/vibbits/material-liascript/master/example-presentation.md#1)

[File on Github](https://github.com/vibbits/material-liascript/blob/master/example-presentation.md?plain=1)

**********************

         --{{1}}--
Text

           {{1}}
*******************

**Exercises**

| ![](../../../assets/images/04-activities.png)<!-- style = "width: 80px; padding:15px;"-->   | Activity: Create a presentation using a markdown dialect called Liascript  |

[Doc about Liascript](https://liascript.github.io/course/?https://raw.githubusercontent.com/liaScript/docs/master/README.md#1)

| ![](../../../assets/images/04-activities.png)<!-- style = "width: 80px; padding:15px;"-->   | Activity: Create a presentation using a Google slides  |

Additional exercise

| ![](../../../assets/images/04-activities.png)<!-- style = "width: 80px; padding:15px;"-->    | Activity: Create a PDF with Liascript (installation needed)   |

*************

## Final considerations

      --{{0}}--
When considering the re-usability and extendability of training materials, PDF documents offer limited flexibility due to their static nature, making them less adaptable for updates or interactive elements. HTML pages provide greater re-usability and extendability, allowing for dynamic content and easier updates. PowerPoint files are somewhat reusable but can be cumbersome to update and share collaboratively. Google Presentations enhance re-usability through cloud-based collaboration and real-time updates, though they still face limitations in format compatibility. Markdown-based material stands out for its high degree of re-usability and extendability, being easily editable, version-controlled, and convertible to various formats. Looking ahead, the future of interoperable training material formats lies in developing standards that ensure seamless integration across platforms. Current gaps include inconsistent formatting, limited support for interactive elements, and challenges in maintaining version control across different tools. Addressing these gaps will be crucial for creating truly interoperable and user-friendly training materials.

![](../../../assets/images/rect2.png)<!-- style="width: 650px;" -->
