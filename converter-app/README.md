# 🎙️ Bobby's Converter

A serverless multi-language text-to-speech application built with AWS services, featuring a React frontend and Lambda backend.

## 🌟 Features

- Convert text to natural-sounding speech using Amazon Polly
- Multiple voice options (Joanna, Matthew, Amy, etc.)
- Audio file generation and download
- Responsive web interface
- Global content delivery via CloudFront CDN

## 🏗️ Architecture

- **Frontend**: React.js hosted on S3 with CloudFront distribution
- **Backend**: AWS Lambda function with Python
- **Text-to-Speech**: Amazon Polly
- **Storage**: S3 bucket for audio files
- **API**: API Gateway for REST endpoints
- **Infrastructure**: Terraform for IaC

## 🚀 Live Demo

- **CloudFront URL**: https://d1cj82rr9g62ag.cloudfront.net
- **API Endpoint**: https://eljnjr8mg4.execute-api.us-east-1.amazonaws.com/prod

## 📁 Project Structure

```
Esi Kodiah - Text-to-Speech Project/
├── backend/                 # Terraform infrastructure
│   ├── lambda.tf           # Lambda function configuration
│   ├── s3.tf              # S3 bucket setup
│   ├── api.tf             # API Gateway configuration
│   └── lambda.py          # Lambda function code
├── frontend/               # Frontend infrastructure
│   ├── cloudfront.tf      # CloudFront distribution
│   └── s3.tf             # Frontend S3 bucket
└── react/                 # React application
    ├── src/
    │   ├── components/    # React components
    │   ├── app.js        # Main app component
    │   └── config.js     # API configuration
    └── public/           # Static files
```

## 🛠️ Technologies Used

- **Frontend**: React.js, CSS3, HTML5
- **Backend**: Python 3.11, AWS Lambda
- **Cloud Services**: AWS S3, CloudFront, API Gateway, Polly
- **Infrastructure**: Terraform
- **Build Tools**: npm, Create React App

## 📋 Prerequisites

- AWS CLI configured
- Node.js and npm installed
- Terraform installed
- AWS account with appropriate permissions

## 🚀 Deployment

### Backend Infrastructure
```bash
cd backend
terraform init
terraform apply
```

### Frontend Infrastructure
```bash
cd frontend
terraform init
terraform apply
```

### React Application
```bash
cd react
npm install
npm run build
aws s3 sync build/ s3://your-frontend-bucket --delete
aws cloudfront create-invalidation --distribution-id YOUR_ID --paths "/*"
```

## 🎯 Usage

1. Visit the application URL
2. Enter text in the textarea
3. Select a voice from the dropdown
4. Click "Convert to Speech"
5. Play or download the generated audio

## 🔧 Configuration

Update `react/src/config.js` with your API Gateway URL:
```javascript
export const API_CONFIG = {
  API_GATEWAY_URL: 'https://your-api-id.execute-api.region.amazonaws.com/prod'
};
```

## 📊 AWS Resources

- **S3 Buckets**: 2 (frontend hosting, audio storage)
- **Lambda Function**: 1 (text-to-speech processing)
- **API Gateway**: 1 REST API
- **CloudFront**: 1 distribution
- **IAM Roles**: 1 (Lambda execution)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 👨‍💻 Author

**Bobby's Converter Team**
- AWS Cloud Computing Program Project
- Multi-Language Text-to-Speech Implementation

## 🙏 Acknowledgments

- AWS for cloud services
- Amazon Polly for text-to-speech capabilities
- React community for frontend framework