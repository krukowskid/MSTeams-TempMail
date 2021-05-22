# MSTeams-TempMail
Pretty easy solution for temporary / disposable mailbox on Microsoft Teams channel.

I had to create private temporary email solution for dev/test environments. Our testers were using portals like getnada but we wanted to keep all emails private. There are some "self-hosted" solutions, but they require server to run and don't have built-in authentication capability. This solution is using Exchange Online (but it could be any mail server).

## Steps
1. Add and authenticate new domain in Office365
2. Set domain as `Internal Relay` in Exchange 
3. Enable Email integration in [Teams Admin center](https://admin.teams.microsoft.com/company-wide-settings/teams-settings)
4. Create new channel in Teams and download e-mail address of channel
5. Open advanced settings and configure who can send emails to this channel 
6. Create new mail flow rule in Exchange - if recipient domain is `temp.yourdomain.pl` then redirect message to `Teams channel email`

Now you should recieve all emails sent to `*@temp.yourdomain.pl` in your new Teams channel!
