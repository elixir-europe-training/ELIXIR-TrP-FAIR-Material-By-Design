!!! success "Learning Outcomes"

    - List common e-learning platforms
    - Explain what the SCORM format is 
    - Describe pros and cons of different Learning Management Systems, from a FAIR perspective
    - Create a github page to host and deliver training
    - Describe how to make your training material FAIR using only google drive



## Presentation
Here you can find the presentation for this session:

<iframe src="https://drive.google.com/file/d/1f9OQH3KgY5wJiFnCM9X6TpGxa63ahPfwnutMmt9eQ6U/preview" width="640" height="360" allow="autoplay"></iframe>

The full presentation can be downloaded as a pdf [here](https://drive.google.com/file/d/1f9OQH3KgY5wJiFnCM9X6TpGxa63ahPfwnutMmt9eQ6U/export?format=pdf).


## Hosting and delivery

When it comes to hosting and delivering training materials in line with FAIR principles, there are several tools and platforms that can help ensure your content is well-organized and accessible. Hosting your materials can involve cloud-based platforms like **G Suite** or **Nextcloud**, which are ideal for collaboration and real-time editing. These platforms allow users to store documents, presentations, and other data in one place, making it easier for teams to work together on developing course materials.

For more technical users, **GitHub** offers a robust version control system that allows for collaborative development and easy sharing of materials. This platform is particularly useful for archiving content, as it keeps a history of all changes made, ensuring that different versions of the materials are available for future use or review.

On the delivery side, a **Learning Management System (LMS)** is often the go-to platform. Popular LMS platforms like **Moodle**, **Canvas**, and **OpenEDX** help educators manage and deliver content to students, track learner progress, and create a more engaging learning experience. For those who prefer an open, web-based approach, **GitHub Pages** allows you to turn a GitHub repository into a simple website, making it a lightweight yet powerful solution for course delivery.


### The training life cycle

Training materials go through several phases in their lifecycle: development, delivery, sharing, and archiving. In the **development** phase, tools like G Suite or GitHub allow for collaborative creation of content. Once the materials are ready, they move into the **delivery phase**, where LMS platforms or GitHub Pages are used to distribute them to learners. The **sharing** phase ensures that materials are made publicly available, often through platforms like Zenodo, GitHub, or even a public LMS site. Finally, in the **archiving** phase, content is stored for future use, ensuring it remains accessible and reusable for future trainers or trainees.

### Learning Management systems and google drive

Using google drive alongside an LMS can enhance the delivery and management of training materials. google drive provides a collaborative environment for creating course content — such as documents, presentations, and exercises — which can then be shared via a more structured LMS like Moodle or OpenEDX. The combination of these tools ensures that the content remains easily accessible and organized, while the LMS provides tools to track learner engagement and progress. Both systems support various file types and have flexible access control options, ensuring that materials remain FAIR-compliant.

To ensure interoperability and flexibility, training materials should comply with e-learning standards. **SCORM** is a widely used standard that packages content in a way that allows it to be used across different LMS platforms. **xAPI** is a newer standard that tracks diverse learning experiences, both within and outside the LMS environment. **CMI5** combines the best aspects of SCORM and xAPI, supporting traditional LMS features while also allowing for more flexible, modern learning environments. These standards ensure that your content remains interoperable and reusable across different platforms and learning scenarios.

### GitHub and GitHub pages

For trainers looking to develop, share, and archive content in a more open environment, GitHub offers tools for collaborative content development. GitHub Pages provides a simple way to turn your repository into a website, making it an excellent tool for delivering course materials. Best practices for working with GitHub include using releases to create different versions of course materials and enabling collaboration by allowing multiple contributors to work on the same content. GitHub also supports public access and indexing by search engines, making your materials findable and accessible to a wide audience.


## Discussion topics

|              | Findable    |  Accessible  | Interoperable  | Reusable | 
| -----------  | ----------- | -----------  | -------------- | -------- |
| Google drive | No, not searchable  | | | |
| Github       |   | Yes, can be made public <br>and accessible to all | | |
| LMS          |   | | | Exported in SCORM <br>format |

How do the above hosting and delivery alternatives do when looked at through the FAIR principles? Fill in the missing cells.

## Case studies

Below is three case studies of trainers setting up and delivering courses. Analyze each case and judge how FAIR it is when it comes to the training materials life cycle.

### RNAseq analysis course

Kate has an onsite course in RNAseq analysis. She sends out all relevant course information by email to the students. During the course she has prepared powerpoint slides for her presentations, and exercise instructions that she has in a google drive folder she shares with her students. After the course is done, she sends the slides as pdfs to her students.

### Microscopy course

Steve has a course in microscopy, delivered online. He also has a google drive folder where he prepares all his slides, exercises, and other relevant information regarding the course. This folder is read-only for anyone with the link. He sets up a course website in Canvas, where he links all information from his google drive, including presentation slides and exercises. The course website he makes public so everyone can see it. Plus, he links to the original google drive folder from Canvas.

### R course

Jane has a hybrid course in R. She has set up a course website using github pages and Quarto. She has a github repo where she creates all information regarding the course, including slides and exercises using markdown. She uses releases to separate different instances of her course. All relevant information is published on the github page, with the links to the github repo.

## Exercise: Set up a course website

Now once you have your course syllabus and learning outcomes, it's time to set up a course website where we can display all this information. A course website helps make your training findable and accessible for your students and the rest of the world.

Depending on your technical skills and preferences, you may choose either of these 3 options below for hosting your website:

### Different prerequisities


<div style="background-color:lightgreen; padding-top:7px; padding-bottom:1px; padding-left:15px; border-radius:10px;margin-bottom:10px;">
<b>Easy technical</b><br>
No knowledge of github needed
</div>

<div style="background-color:#F8C471; padding-top:7px; padding-bottom:1px; padding-left:15px; border-radius:10px;margin-bottom:10px;">
<b>Intermediate technical</b><br>
Basic knowledge of github needed (clone, push, pull) + basic markdown skills
</div>

<div style="background-color:#D98880; padding-top:7px; padding-bottom:1px; padding-left:15px; border-radius:10px;margin-bottom:10px;">
<b>Advanced technical</b><br>
Intermediate knowledge of github needed (clone, push, pull, gh-pages configuration) + basic quarto knowledge
</div>
<br>

### Using OpenEdx and Google drive (easy)

Your organization might have their own LMS set up for you to use, but here we will just try the process out by using the Open edX sandbox, which is designed for testing out setting up your own courses. You will not be able to use this for your real courses, as the data is deleted every day (*which also means whatever you put in here today you will unfortunately also have to re-do tomorrow, so don't add too much information today*).

Steps:

1. Create a Google drive folder where you will put the course materials
2. Create a user account at [https://sandbox.openedx.org/]()
3. Go to the tab Studio and click the `Create your first course` button
4. Fill in the information required and create the course
5. Make sure you have your course syllabus and learning outcomes in separate documents in the Google drive folder
6. Embed the syllabus and learning outcomes documents in iframes.
   - In google: File -> Share -> Publish to web. Click on the Embed tab, and copy the code
   - In Open edX: add new section, subsection, and unit
   - Name the units Syllabus and Learning outcomes, and add a Text element to each
   - Edit the page and click Embed iframe in the top right corner
   - Paste the embed code from google
   - You might have to adjust the size:
   ```
   <iframe src="<url>" width="900px" height="900px" scrolling="no" frameborder="0"></iframe> 
   ```

<br>

### Using github and Liascript (intermediate)

#### Create repo 
Create a github repo from template at [https://github.com/vibbits/training_material_template](). Make sure the repo is public.

#### Clone the repo
Clone the repo to your local computer.

#### Generate course website
Copy the url of the raw README.md page on github and paste it here: [https://liascript.github.io/](). You can use the generated url to send to your course participants. The website will be generated locally on their computers, directly from github.

#### Add learning outcomes
Update the README.md file on your computer to add learning outcomes and syllabus. Push the changes to github to make them render on the course website. You might have to force refresh your browser to see the changes on the site.

<br> 

### Using github pages and Quarto (advanced)

If you choose this option we assume you are experienced enough to create a repo, start a new Quarto project, and set up a gh-pages to display the course website. You can find the Quarto documentation for setting up a website [here](https://quarto.org/docs/websites/).

A few things you should consider when creating the quarto pages:

- Make sure to add authors where applicable
- Add a page with your Learning outcomes and course syllabus

You can use the Liascript template from the previous option as inspiration.

