# EmailJS Setup Instructions

Your contact form has been updated to use EmailJS instead of PHP. Follow these steps to complete the setup:

## 1. Create EmailJS Account
1. Go to https://www.emailjs.com/
2. Sign up for a free account (200 emails/month free)
3. Verify your email address

## 2. Create Email Service
1. In EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow setup instructions to connect your email
5. Note down your **Service ID**

## 3. Create Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Use this template content:

**Subject:** Website Enquiry - agalchemyconsults.com

**Content:**
```
New Contact Enquiry

Full Name: {{from_name}}
Email Address: {{from_email}}
Phone Number: {{phone}}
Project Type: {{project_type}}
Location: {{location}}
Estimated Budget: {{budget}}

Message:
{{message}}
```

4. Save template and note down your **Template ID**

## 4. Get Your Public Key
1. Go to "Account" > "General"
2. Find your **Public Key**

## 5. Update Configuration
In `contactus.html`, replace these placeholders:

```javascript
emailjs.init("YOUR_PUBLIC_KEY"); // Replace with your actual public key
emailjs.send("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", templateParams)
```

With your actual values:
```javascript
emailjs.init("your_actual_public_key");
emailjs.send("your_service_id", "your_template_id", templateParams)
```

## 6. Test the Form
1. Open `contactus.html` in a web browser
2. Fill out the contact form
3. Submit and verify emails are received at veegov@agalchemyconsults.com

## Benefits of EmailJS
- ✅ No server required
- ✅ Pure client-side JavaScript
- ✅ Free tier (200 emails/month)
- ✅ Reliable email delivery
- ✅ Easy to maintain

## Security Note
The public key is safe to expose in client-side code. EmailJS handles authentication securely on their servers.