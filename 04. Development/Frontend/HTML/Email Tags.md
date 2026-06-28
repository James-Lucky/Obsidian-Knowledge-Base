**Basic mailto link:**

html

```html
<a href="mailto:user@example.com">Send Email</a>
```

**With subject:**

html

```html
<a href="mailto:user@example.com?subject=Hello%20There">Send Email</a>
```

**With subject + body:**

html

```html
<a href="mailto:user@example.com?subject=Hello&body=This%20is%20the%20message">Send Email</a>
```

**Multiple recipients:**

html

```html
<a href="mailto:user1@example.com,user2@example.com">Send Email</a>
```

**CC and BCC:**

html

```html
<a href="mailto:user@example.com?cc=cc@example.com&bcc=bcc@example.com">Send Email</a>
```

**Everything combined:**

html

```html
<a href="mailto:user@example.com?subject=Project%20Update&body=Check%20this%20out&cc=manager@example.com">Send Email</a>
```

**Important details:**

- Spaces must be `%20` (URL encoded)
- Use `&` to separate parameters
- No `<email>` tag exists—it's just `<a>` with `href="mailto:"`
- Opening the user's default email client—you don't send directly from the browser
- Subject and body get URL-encoded, so special characters need encoding

**URL encoding common characters:**

- Space: `%20`
- &: `%26`
- =: `%3D`
- ?: `%3F`
- #: `%23`

**Reality check:** Mailto links are dinosaur tech. If you're building anything serious:

- Users often don't have a default email client configured
- Mobile handling varies wildly
- Better approach: form submission to your backend → server sends email via SMTP