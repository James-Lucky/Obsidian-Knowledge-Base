
// import emailjs from '@emailjs/browser';

const Result = () => {
    return (
        <p className='send_alert'>Your message has been successfully sent !</p>
    )
}

const ContactForm = () => {

    const [result, showResult] = useState(false);
    const sendEmail = (e) => {
        e.preventDefault();

        emailjs.sendForm('', '', e.target, '')
            .then((result) => {
                console.log(result.text);
            }, (error) => {
                console.log(error.text);
            });
        e.target.reset();
        showResult(true)
    };

    //hide result
    setTimeout(() => {
        showResult(false)
    }, 5000)

### Email js template

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact Email</title>
</head>
<body style="margin: 0; padding: 0; background-color: #f4f4f4;">
    <table role="presentation" width="100%" cellspacing="0" cellpadding="0" border="0" style="background-color: #f4f4f4; padding: 20px;">
        <tr>
            <td align="center">
                <table role="presentation" width="600" cellspacing="0" cellpadding="0" border="0" style="background-color: #ffffff; padding: 20px; border-radius: 10px; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);">
                    <tr>
                        <td align="center" style="padding-bottom: 20px;">
                            <img src="https://redsecureme.netlify.app/logo.png" alt="Company Logo" style="max-width: 150px;">
                        </td>
                    </tr>
                    <tr>
                        <td align="center" style="font-family: Arial, sans-serif; font-size: 24px; font-weight: bold; color: #333;">
                          <hr/>
                            Contact Form Submission
                        </td>
                    </tr>
                    <tr>
                        <td style="padding: 20px 0; font-family: Arial, sans-serif; font-size: 16px; color: #555;">
                            <p><strong>Name:</strong> {{full-name}}</p>
                            <p><strong>Phone:</strong> {{mobile}}</p>
                            <p><strong>Email:</strong> {{email}}</p>
                            <p><strong>Message:</strong></p>
                            <p>{{message}}</p>
                        </td>
                    </tr>
                    <tr>
                        <td align="center" style="padding: 20px 0;">
                            
                        </td>
                    </tr>
                    <tr>
                        <td align="center" style="padding-top: 20px; font-family: Arial, sans-serif; font-size: 14px; color: #555; border-top: 1px solid #ddd;">
                            <p>Company Phone: +971 50 948 3857</p>
                            <p>Email: sales@redsecureme.com</p>
                              <p> HQ Al Fajer complex, 1st Floor Office - 105, Oud Metha Dubai, UAE</p>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```