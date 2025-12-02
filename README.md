# Resume Generator

A modern, customizable resume/CV generator that creates professional PDF-ready resumes from a simple configuration file. Perfect for developers, engineers, and professionals who want a clean, ATS-friendly resume.

## Features

- 📄 **Easy Configuration** - Edit your resume data in a simple JavaScript config file
- 🎨 **Professional Design** - Clean, modern two-column layout
- 📱 **Responsive** - Works on all screen sizes
- 📥 **PDF Export** - Download your resume as a PDF with one click
- 🔍 **ATS-Friendly** - Hidden metadata for better parsing by Applicant Tracking Systems
- 🎯 **Customizable** - Full control over content, styling, and layout
- ⚡ **No Build Step** - Pure HTML, CSS, and JavaScript - just open and use

## Quick Start

### 1. Clone or Download

```bash
git clone https://github.com/sirghiea/ResumeGenerator.git
cd ResumeGenerator
```

### 2. Edit Your Resume Data

Open `config.js` and update it with your information:

```javascript
var cvConfig = {
    name: "Your Name",
    title: ["Your Title", "Contractor", "Freelancer"],
    contact: {
        phone: "+1 234 567 8900",
        email: "your.email@example.com",
        // ... more contact info
    },
    // ... rest of your resume data
};
```

### 3. Add Your Profile Photo

Place your profile photo in the `img/` folder and name it `profile.jpg` (or update the path in `index.html`).

### 4. Open in Browser

Simply open `index.html` in your web browser, or use a local server:

```bash
# Using Python
python3 -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server
```

Then visit `http://localhost:8000` in your browser.

### 5. Download PDF

Click the "Download PDF" button in the top-right corner to generate and download your resume as a PDF.

## File Structure

```
ResumeGenerator/
├── index.html          # Main HTML file with resume template
├── config.js           # Your resume data (edit this!)
├── img/
│   └── profile.jpg     # Your profile photo
├── resume-template.txt # Template file for easy editing
└── README.md           # This file
```

## Configuration Guide

### Personal Information

```javascript
name: "Your Full Name",
title: ["Title 1", "Title 2", "Title 3"], // Multiple titles separated by |
```

### Contact Information

```javascript
contact: {
    phone: "+1 234 567 8900",
    whatsapp: "+1 234 567 8900",      // WhatsApp number
    telegram: "your_username",         // Telegram username (without @)
    email: "your.email@example.com",
    location: "City, Country",
    linkedin: "in/your-profile",        // LinkedIn profile path
    medium: "@your-username",          // Medium username
    github: "your-username",           // GitHub username
    githubLink: "https://github.com/your-username"
}
```

### About Me

```javascript
aboutMe: [
    [
        { type: "normal", content: "Regular text " },
        { type: "bold", content: "bold text" },
        { type: "normal", content: " more regular text." }
    ],
    // Add more paragraphs as needed
]
```

### Skills

You can use two types of skills:

**Normal Skills** (calculated from work experience):
```javascript
skills: [
    { type: "normal", name: "React" },
    { type: "normal", name: "Python" }
]
```

**Custom Skills** (with specified years):
```javascript
skills: [
    { type: "custom", name: "React", years: 8 },
    { type: "custom", name: "Python", years: 6 }
]
```

### Education

```javascript
education: [
    {
        university: "University Name",
        degree: "Degree Name",
        locAndYears: "Location, 2015 - 2019"
    }
]
```

### Work Experience

```javascript
experience: [
    {
        pageBreak: false,  // Set to true to add page break before this entry
        position: "Job Title",
        period: [{ month: 1, year: 2020 }, { month: 12, year: 2021 }], // or { month: 12, year: 2024 } for "Present"
        project: "Project Name",
        company: "Company Name",
        description: "Project description...",
        impact: [
            [
                { type: "bold", text: "Achievement in bold" },
                { type: "normal", text: " rest of the description." }
            ]
            // Add more impact points
        ],
        skills: ["Skill1", "Skill2", "Skill3"]
    }
]
```

**Important:** Make sure work experience dates don't overlap! Leave at least 1 month gap between projects.

## Using the Template File

For easier editing, you can use the `resume-template.txt` file:

1. Open `resume-template.txt`
2. Fill in all sections with your information
3. Save the file
4. The template can be parsed to automatically update `config.js` (or manually copy the data)

## PDF Generation

The resume generator uses [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) to create PDFs. Features:

- **Page Break Control** - Sections automatically move to next page if they don't fit
- **High Quality** - 2x scale for crisp text and images
- **A4 Format** - Standard resume size
- **Print-Ready** - Optimized for printing

## ATS Optimization

The resume includes hidden metadata with all technology keywords for better parsing by Applicant Tracking Systems (ATS). This metadata is:

- Hidden from human view (positioned off-screen)
- Visible to resume scanners
- Automatically generated from your skills and work experience

## Customization

### Changing Colors

Edit the CSS in `index.html`:

```css
.shortInfoBlock > .title {
    color: rgb(91, 194, 251);  /* Change this color */
}
```

### Changing Fonts

Update the font-family properties in the CSS section of `index.html`.

### Adjusting Layout

Modify the width values in the CSS:

```css
.shortInfo {
    width: 70mm;  /* Left column width */
}
.xp {
    width: 140mm;  /* Right column width */
}
```

## Browser Compatibility

- ✅ Chrome/Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Opera

## Troubleshooting

### PDF Download Not Working

- Make sure you're using a modern browser
- Check browser console for errors
- Try disabling browser extensions

### Dates Overlapping Error

If you see an error about overlapping projects:
- Check your work experience dates in `config.js`
- Ensure there's at least 1 month gap between projects
- Adjust the end date of one project or start date of the next

### Skills Showing "NaN year"

- Make sure custom skills have the `years` property set
- For normal skills, ensure they appear in at least one work experience entry

### Profile Image Not Showing

- Check that `img/profile.jpg` exists
- Verify the file path in `index.html`
- Ensure the image file is a valid image format (jpg, png, etc.)

## Contributing

Feel free to fork this project and customize it for your needs! If you have improvements, pull requests are welcome.

## License

This project is open source and available for personal and commercial use.

## Support

For issues or questions, please open an issue on [GitHub](https://github.com/sirghiea/ResumeGenerator).

---

**Created by** [Alexandru Sirghie](https://github.com/sirghiea)

