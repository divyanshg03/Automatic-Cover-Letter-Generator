# Automatic-Cover-Letter-Generator
# Automated Job Application Workflow

An intelligent n8n automation workflow that streamlines the job application process by automatically scraping LinkedIn job postings, extracting job details using AI, and generating personalized cover letters.
<img width="1824" height="774" alt="image" src="https://github.com/user-attachments/assets/e036e5ad-6d55-4480-8823-d6232d874041" />

## 🚀 Features

- **Automated Job Scraping**: Scrapes LinkedIn job postings for internship positions using Apify actors
- **AI-Powered Data Extraction**: Uses Google Gemini AI to extract structured job information
- **Personalized Cover Letter Generation**: Creates customized cover letters based on job requirements and candidate profile
- **Google Sheets Integration**: Automatically saves generated cover letters to a Google Spreadsheet
- **Scheduled Execution**: Runs automatically at 10 AM daily using schedule triggers

## 🛠 Technology Stack

- **Automation Platform**: n8n workflow automation
- **Web Scraping**: Apify LinkedIn Jobs Scraper
- **AI/ML**: Google Gemini 2.0/2.5 Flash models
- **Data Storage**: Google Sheets API
- **APIs**: LinkedIn Jobs API (via Apify)

## 📋 Workflow Components

### 1. Schedule Trigger
- Runs daily at 10:00 AM
- Initiates the entire job application workflow

### 2. Job Scraping (Apify Integration)
- Uses LinkedIn Jobs Scraper actor
- Searches for internship positions in specified location
- Scrapes up to 200 job postings
- Includes company information and job details

### 3. AI Data Processing
- **First AI Model**: Extracts structured data from job postings
  - Company name
  - Benefits
  - Location
  - Job description
- **Second AI Model**: Generates personalized cover letters
  - Uses candidate's resume data
  - Customizes content based on job requirements

### 4. Data Management
- Loops through scraped job postings
- Applies rate limiting and wait times to avoid API limits
- Updates Google Sheets with generated cover letters

## 🎯 Target Use Case

This workflow is designed for job seekers, particularly students and new graduates seeking internship opportunities. The system:

- Automatically finds relevant internship positions
- Generates tailored cover letters highlighting relevant skills based on candidate profile
- Customizes applications based on job requirements and candidate background
- Streamlines the application process for multiple positions

## ⚙️ Configuration

### Required Credentials
- **Apify API**: For LinkedIn job scraping
- **Google Gemini API**: For AI-powered text generation
- **Google Sheets OAuth2**: For spreadsheet integration

### Key Parameters
- **Search Location**: Currently set to India (geoId: 105214831)
- **Job Type**: Internships with remote/hybrid options
- **Batch Size**: 200 jobs per execution
- **Rate Limiting**: 2-second delays between API calls

## 📊 Output Format

The workflow generates data in the following structure:

### Job Data Extraction
```json
{
  "company_name": "Company Name",
  "benefits": "List of benefits",
  "location": "Job location",
  "job_description": "Detailed description"
}
```

### Cover Letter Output
```json
{
  "cover_letter": "Personalized cover letter content"
}
```

## 🔄 Workflow Process

1. **Trigger**: Schedule activates at 10 AM
2. **Scrape**: Fetch job postings from LinkedIn
3. **Wait**: Brief delay for API rate limiting
4. **Loop**: Process each job posting individually
5. **Extract**: AI extracts job details
6. **Generate**: AI creates personalized cover letter
7. **Save**: Update Google Sheets with results

## 📈 Performance Features

- **Batch Processing**: Handles multiple job postings efficiently
- **Rate Limiting**: Prevents API throttling with built-in delays
- **Error Handling**: Includes timeout settings and retry mechanisms
- **Data Validation**: Ensures structured output from AI models

## 🎓 Candidate Profile Integration

The workflow includes a candidate profile system that can be customized with:

- **Education**: University, degree, and academic performance
- **Skills**: Technical skills relevant to target positions
- **Projects**: Portfolio projects and accomplishments
- **Achievements**: Academic and professional milestones
- **Experience**: Relevant work experience and leadership roles

## 🔧 Customization

To adapt this workflow for different users:

1. Update the candidate profile in the cover letter generation node
2. Modify search parameters for different job types/locations
3. Adjust the Google Sheets document ID
4. Update AI model prompts for different industries

## 📝 Setup Instructions

1. **Install n8n**: Set up n8n workflow automation platform
2. **Import Workflow**: Load the `My workflow.json` file
3. **Configure Credentials**: Add API keys for all services
4. **Update Parameters**: Modify search criteria and candidate info
5. **Test Execution**: Run manually before scheduling

## 🚨 Important Notes

- Ensure compliance with LinkedIn's terms of service
- Monitor API usage to avoid rate limits
- Regularly update candidate profile information
- Review generated cover letters for accuracy

## 📞 Support

For questions about this workflow automation project:
- Check the documentation above for setup and configuration details
- Refer to n8n documentation for workflow customization
- Consult API documentation for individual services used

---

*This automation workflow helps streamline the job application process, allowing candidates to focus on interview preparation while the system handles initial application generation and organization.*
