# Awareness Template Customization

## Editing an Awareness Template

You can customize awareness templates in two ways:

1. **Copy an existing template** and modify it to fit your needs.
2. **Create a new template** and build it from scratch.

Copying an existing template is the fastest option if you only need to adjust content or structure. Creating a new template gives you full control over the layout and messaging.

{% hint style="info" %}
**Tip:** Many awareness templates include custom JavaScript and CSS used for tracking statistics and ensuring proper functionality. To avoid breaking these features, it is recommended to **copy and modify an existing template** instead of creating one from scratch.
{% endhint %}

Choose one of the options below to get started.

***

## Copy an Existing Template

You can duplicate an existing template and modify the copy without affecting the original.

#### Steps

1. Search for the template you want to copy in the **Template Gallery**.
2. Select the template from the results.
3. Open the **Actions** dropdown menu.
4. Click **Copy**.

{% hint style="info" icon="check" %}
The time required to create the copy depends on the size of the template and may take a few minutes. Video and SCORM templates generally take the longest.

When the process is complete, a green banner will appear with the message **“Finished Successfully.”**
{% endhint %}

#### Identifying the Copied Template

After the copy is created, searching for the template will show both versions:

* The **original template**
* The **copied template**, labeled with **“(copy)”** added to the title

#### Editing the Copied Template

To modify the copied version:

1. Select the copied template.
2. Click **Edit Template**.

This opens the template editor where you can update the content, layout, or settings as needed.

***

## Create a New Template

To build a template from scratch:

1. Click **Create Template**.
2. On the next page, complete the template metadata fields.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

#### General Info

{% hint style="info" %}
These fields define the core properties of the template.
{% endhint %}

**Icon**\
Upload an image file to use as the template icon. This icon will appear in the **Template Gallery**.

**Name**\
Enter a name for the template.

**Type**\
Select the template type from the dropdown menu.

**Client**\
Assign the template to a specific client or make it available to all clients by selecting **All**.

**SCORM Version**\
If the template uses SCORM, select the appropriate SCORM version.

**Platform**\
Choose whether the template is intended for **Desktop**, **Mobile**, or **both**.

**Description**\
Provide a short description of the template.

***

#### Quiz Settings

These settings apply if the template includes a quiz.

**Quiz**\
Enable this option if the template will include a quiz.

**Extended Tracking Method**\
If the **Quiz** option is enabled, you can optionally enable extended quiz tracking.\
Refer to the [extended quiz tracking guide](use-extended-method-of-tracking-the-end-of-the-quiz.md) for more information.

**Minimum Correct Answers**\
By default, users receive credit for completing the quiz. You can set a minimum number of correct answers to require a passing score.

***

#### Template Language

Select all languages supported by the template.

If multiple languages are selected, translated content must be provided for each language. This can be done manually or by using the [**AI Translation**](../../application-reference/templates/automatic-translation.md) feature.

***

#### Template Attributes (Optional)

{% hint style="info" %}
These settings help categorize templates and make them easier to find in the **Template Gallery**.
{% endhint %}

**Difficulty Level**\
Select **Low**, **Medium**, or **High** depending on the intended difficulty.

**Content**\
Choose the relevant content types (for example, **Meetings** or **Social Media**).

**Sender**\
Select the sender type associated with the template (for example, **HR** or **Legal**).

**Target Audience**\
Select the intended audience (for example, **End Users** or **Management**).

**Duration**\
Provide the estimated time required to complete the template.

**Brands**\
Select any brands the template is intended to replicate. This option is typically used for **attack templates**.

***

## Customizing the Email Content

The **Email Template** section allows you to configure the email that users will receive as part of the awareness campaign. Each language version of a template has its own email content, so you must configure the content separately for every supported language.

#### Language

Use the **Language** dropdown to select which language version of the email you want to edit.

Email content is **not automatically translated or synchronized between languages**. If your template supports multiple languages, you must create and maintain the content for each language individually.

***

#### Email Settings

**Subject**\
Enter the subject line that will appear in the recipient’s inbox.

**Sender Name**\
Specify the display name that appears as the sender of the email.

**Sender Email**\
Enter the email address that will be used to send the message.

**Editor Type**\
Choose the editing method for the email content. The **Visual Editor** allows you to design the email using a WYSIWYG interface.

***

#### Email Content Editor

Use the editor to create and format the body of the email. This area supports typical formatting options such as text styling, links, images, and layout adjustments.

***

#### AI Translation

If your template supports multiple languages, you can use the **AI Translation** option to help generate translated versions of the email content. Translations should always be reviewed to ensure accuracy.

***

#### Attachments

The **Attachments** section allows you to include files or embedded images with the email.

**Embedded Images**\
Displays images currently embedded in the email content.

**Attachments**\
Lists files that will be attached to the email.

**Add Attachment**\
Click **Choose file** to upload a file that will be included as an attachment in the email.

{% hint style="info" %}
After editing the email content, click **Save** to apply your changes to the template.

Once the email content is saved, you can use the **Preview** button to review how the email will appear to recipients.
{% endhint %}

***

## Customizing the Content Template

The **Content Template** section controls the awareness webpage that users will see when they open the training or awareness content. This page can include text, images, videos, and interactive elements such as quizzes.

#### Language

Use the **Language** dropdown to select which language version of the webpage you want to edit.

Each language maintains its **own independent content**. Changes made to one language will **not automatically apply to other languages**, and translations must be created separately.

***

#### File

The **File** dropdown allows you to select which file from the template package you want to edit.

Most templates use **`index.html`** as the main entry point for the awareness content.

If the template contains multiple files, you can select and edit each file individually from this dropdown.

***

#### Editor Type

Select how you want to edit the webpage content.

**Visual Editor**\
A WYSIWYG editor that allows you to modify content visually without directly editing HTML code.

**Code Mirror**\
A code editor that allows you to directly edit the template’s HTML, CSS, and JavaScript.

***

#### Content Editor

The **Content** editor is where you modify the webpage content itself. You can use the editor toolbar to:

* Format text (bold, italics, headings, etc.)
* Insert links and images
* Upload files or media
* Add tables and other formatting elements
* Insert [system variables](../../application-reference/templates/variables-in-lucy.md) where supported

***

#### AI Translation

If the template supports multiple languages, the **AI Translation** option can assist in generating translated versions of the webpage content. Translated content should always be reviewed for accuracy before publishing.

***

#### Upload Webpage

If you want to replace the existing webpage content entirely, you can use **Upload Webpage** to upload a packaged HTML webpage for the template.

This is typically used when importing externally designed awareness content.

Uploaded content must be in a `.zip` file and include an `index.html` file.

***

#### Export to SCORM

The **Export to SCORM** option allows you to export the awareness content as a **SCORM package**, which can be used in external Learning Management Systems (LMS).

***

#### Previewing the Content

Click **Preview** to view how the webpage will appear to users before saving your changes.

You must save the content first before previewing in order to see your changes.

***

## Editing Advanced Awareness Templates

Some awareness templates contain multiple pages, interactive elements, and quiz logic. These templates require edits to the underlying HTML, CSS, or JavaScript files rather than simple visual changes.

{% hint style="success" %}
If you need assistance customizing a template, contact [**Lucy Support**](../../contact-us.md).
{% endhint %}

***

#### Updating the Logo

You can update the logo displayed on the landing page by editing the **`index.html`** file.\
Changes made to the logo in this file will apply across all training pages that reference it.

<figure><img src="../../.gitbook/assets/chrome_di5sRQ7mMi.gif" alt=""><figcaption></figcaption></figure>

***

#### Changing the Color Scheme

To modify the default color scheme, edit the **`style.css`** file included in the template.

To identify which elements control specific parts of the page:

1. Open the template in your browser.
2. Use your browser’s **Developer Tools** to inspect the page.
3. Locate the CSS classes or styles responsible for the colors you want to change.
4. Update the corresponding styles in **`style.css`**.

<figure><img src="../../.gitbook/assets/image (55) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (54) (1).png" alt=""><figcaption></figcaption></figure>

***

#### Editing lesson content

Each lesson in the template corresponds to a separate HTML file within the template package.

To identify which file controls a specific lesson page:

1. Open **`index.html`** in a browser tab.
2. Use the browser’s **Developer Tools** to inspect the navigation or lesson links.
3. Identify the referenced HTML file associated with the lesson.
4. Open and edit that file to update the lesson content.

<figure><img src="../../.gitbook/assets/image (403).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (402).png" alt="" width="563"><figcaption></figcaption></figure>

***

#### Editing the quiz/exam questions

The question bank is stored in the **`exam.js`** file within the template.

To modify quiz content:

1. Open **`exam.js`** in the editor.
2. Use your browser or editor search function to locate a question or keyword.
3. Edit the question text, answers, or correct answer value.

Each question is structured like so:

```
{ 
    question: "Your PC at home is behaving strangely and you urgently need to finish a document for work. You are not allowed to:",
    answer: 4,
    type: "radio",
    answers: [
        "Go back to the office and finish the document on the work PC.",
        "Take the business PC home to finish the document.",
        "Edit the document on your private device. If malware is present, it will become apparent when the document is opened at work.",
        "Inform your supervisor and complete the document as quickly as possible the next day."
    ],
    remark: ""
}
```

**Question fields:**

* **question** – The question text displayed to the user
* **answers** – The available answer options
* **answer** – The number corresponding to the correct answer
* **type** – The input type (for example, radio buttons)

Updating these values allows you to modify the quiz questions and answers included in the template.

## Custom Video Content

{% hint style="info" %}
Video templates use JavaScript to track statistics such as whether a user has completed watching a video.

To ensure this tracking functions correctly, it is strongly recommended to **copy an existing video template and replace the video file**, rather than creating a video template from scratch.
{% endhint %}

In this guide we will use the video template **Kevin works from home**.

#### Copy the Video Template

1. Locate the **Kevin Works From Home** template.
2. Select the template, then open the **Actions** dropdown and click **Copy**.
3. Select the copied template and click **Edit Template**.

#### Upload the Video File

1. In the **Content Template** section, click **Upload File or Image**.

<figure><img src="../../.gitbook/assets/image (1055).png" alt=""><figcaption></figcaption></figure>

1. Select **Browse Server**.
2. Click **Upload** and upload your video file.
3. After the upload completes, double-click the file to select it.

<figure><img src="../../.gitbook/assets/image (1054).png" alt=""><figcaption></figcaption></figure>

1. Copy the **entire file path** shown in the upload window.
2. Close the upload window without saving by clicking **Cancel**.

<figure><img src="../../.gitbook/assets/image (1052).png" alt=""><figcaption></figcaption></figure>

#### Update the Video Source

1. Select the **language** you want to edit.
2. In the content editor, switch to **Code Mirror**.
3. Locate the `<video>` element in the HTML.
4. Replace the existing  `src` path with the path you copied.
   1. **Only edit the `<source>` element, do not change the `<video>` element's `class` or `id` !**
5. Save the template after updating the video source.

<figure><img src="../../.gitbook/assets/image (1053).png" alt=""><figcaption></figcaption></figure>
