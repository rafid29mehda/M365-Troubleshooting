Email headers in Outlook contain a wealth of technical details about the message, which can be quite useful for troubleshooting, understanding the path an email has taken, and verifying its authenticity. Here's a breakdown of the key properties you'll find in an email header and what they represent:

1. **From**: Indicates the email address of the sender.
2. **To**: Shows the recipient's email address.
3. **Subject**: The subject line of the email as it appears in the inbox.
4. **Date**: The date and time the email was sent.
5. **MIME-Version**: The version of MIME protocol used to format the email.
6. **Content-Type**: Describes the media type of the email, such as `text/plain` or `text/html`.
7. **Message-ID**: A unique identifier for the email message.
8. **Received**: A series of entries, each one indicating a point that the email passed through, along with the corresponding timestamp.
9. **X-Sender**: The actual email address that sent the message, which might differ from the "From" address.
10. **X-Receiver**: The actual email address that received the message, which might differ from the "To" address.
11. **Return-Path**: The address that bounces will be returned to.
12. **Reply-To**: An address that is set to receive replies if it's different from the "From" address.
13. **Authentication-Results**: Shows the results of SPF, DKIM, and DMARC checks.
14. **X-Spam-Status**: Indicates whether the message was marked as spam.
15. **X-Originating-IP**: The IP address from which the email was sent.

To view the email headers in Outlook:
- Double-click an email message to open it outside of the Reading Pane.
- Click **File > Properties**.
- Header information appears in the **Internet headers** box¹.

For a more detailed analysis, you can use the **Message Header Analyzer** add-in, which breaks down the headers into a more human-friendly view and provides additional information such as the summary, received path, anti-spam details, and other header elements².

Understanding these properties can help you troubleshoot issues, identify potential phishing attempts, and understand the journey an email has taken from sender to recipient.

Source: Conversation with Copilot, 6/4/2024
(1) View internet message headers in Outlook - Microsoft Support. https://support.microsoft.com/en-us/office/view-internet-message-headers-in-outlook-cd039382-dc6e-4264-ac74-c048563d212c.

(2) How to Read Message Headers in Outlook - How-To Geek. https://www.howtogeek.com/442317/how-to-read-message-headers-in-outlook/.

(3) How to view Outlook Email Headers (message headers) - Ablebits. https://www.ablebits.com/office-addins-blog/view-outlook-email-headers/.

(4) View Full Headers in Outlook for Windows | IT@Cornell. https://it.cornell.edu/outlook2016win/view-full-headers-outlook-windows.


Let's delve into the important properties in email headers, including **SCL (Spam Confidence Level)**, **SFV (Spam Filter Verdict)**, and **IFV (Inbound Filter Verdict)**. These properties provide crucial information about how an email was processed and whether it was flagged as spam or malicious.

1. **SCL (Spam Confidence Level)**:
    - The **SCL** is a score assigned by anti-spam engines to indicate the probability that an email is considered spam.
    - It ranges from **-1** (not spam) to **9** (highly likely spam).
    - Lower SCL values indicate legitimate emails, while higher values suggest potential spam.
    - Example: If you see an SCL of **5**, it means the email has a moderate likelihood of being spam³.

2. **SFV (Spam Filter Verdict)**:
    - The **SFV** field provides additional information about the verdict of the spam filter.
    - It includes various categories related to protection policies applied to the message.
    - Examples of SFV values:
        - **SPM**: Indicates the email is marked as spam.
        - **PHSH**: Denotes a high confidence phishing attempt.
        - **MALW**: Flags the email as containing malware.
        - **SPOOF**: Indicates spoofing.
    - Each value corresponds to specific filtering actions taken by the system².

3. **IFV (Inbound Filter Verdict)**:
    - The **IFV** field is part of the X-Forefront-Antispam-Report header.
    - It provides details about the verdict applied to the email during inbound filtering.
    - Example: `IFV:SPM;IPV:NLI;SFV:NSPM;PTR:;SFTY:;`
        - **SPM**: The email is marked as spam.
        - **IPV:NLI**: No link inspection was performed.
        - **SFV:NSPM**: The spam filter verdict is "Not Spam."
        - **PTR**: No reverse DNS lookup was performed.
        - **SFTY**: Safety verdict (additional details not shown here)².

Remember that these properties help administrators and users understand the processing of emails, identify potential threats, and take appropriate actions. If you encounter emails with suspicious SCL or SFV values, consider investigating further or applying additional security measures.

Source: Conversation with Copilot, 6/4/2024
(1) Exchange SCL and EOP headers | Ammar Hasayen. https://blog.ahasayen.com/exchange-scl-eop-headers/.

(2) Anti-spam message headers - Microsoft Defender for Office 365. https://learn.microsoft.com/en-us/defender-office-365/message-headers-eop-mdo.

(3) How to Read Email Message Headers - Practical 365. https://practical365.com/how-to-read-email-message-headers/.




![image](https://github.com/rafid29mehda/M365-Troubleshooting/assets/71279591/9465edb1-cae4-4725-ba0e-0727e4efaddd)

# [Video](https://www.youtube.com/watch?v=QFg-qO3fP5w&list=PL5oyXP-xEiGBt94O8rfGtJT2yfkjiRY2W&index=16)

# [From 12:44](https://www.youtube.com/watch?v=wx7pqji3Uvg&list=PL5oyXP-xEiGBt94O8rfGtJT2yfkjiRY2W&index=16)
