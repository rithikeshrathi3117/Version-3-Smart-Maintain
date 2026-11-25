SMART MAINTAIN - Version L2 deployment package

Files:
1. index.html - Complete website. Equipment QR links now use:
   https://rithikeshrathi3117.github.io/Version-L2-Smart-Maintain/?equipment=EQUIPMENT_ID
2. Code.gs - Complete Google Apps Script backend from the supplied revised file.

Deployment:
- Upload index.html to the root of the GitHub repository:
  rithikeshrathi3117/Version-L2-Smart-Maintain
- Keep GitHub Pages enabled for the repository/root branch.
- Replace Code.gs in the existing Google Apps Script project, deploy a new version,
  and keep the existing /exec web-app URL unchanged in index.html.
- The backend does not require the GitHub Pages URL for spreadsheet synchronization;
  it uses the Google Apps Script /exec endpoint already configured in index.html.

QR behavior:
- Every equipment QR is generated from its stable equipment ID.
- Scanning opens the Version L2 site with ?equipment=<ID>.
- The site reads that ID and opens the matching equipment profile after loading the
  shared Google Sheets register.

CURRENT MAIL SETTING:
- Mandatory daily AMC status email is temporarily disabled by commenting out its
  daily trigger and 15-minute retry trigger in Code.gs.
- AMC expiry reminder email remains enabled.
- When setupSmartMaintain() or reinstallDailyReminderTrigger() is run, any old
  mandatory-mail/retry triggers are deleted and are not recreated.
