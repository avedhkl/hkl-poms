HKL-PoMS - HKL Postgraduate Monitoring System
=============================================

index.html is the interface. It is BUILT, not hand-written: regenerate it with

    python3 /tmp/build_offline_app.py "<apps-script-exec-url>" /home/avteam/master_portal_landing/app

after any change to the Apps Script project, then copy app/index.html here.

Why it is built this way: Google refuses to open Apps Script *pages* for some Workspace
accounts ("Sorry, unable to open the file at present"), but it answers plain, credential-less
POSTs to the same deployment. So this page carries a small shim that talks to the project's
JSON bridge (Api.js) instead of google.script.run. The spreadsheet and all the code stay on
Google; only the interface is served from here.

Keep this public: it contains no data and no credentials. Everything it shows comes from the
API after a person signs in with their own name/email, name/NSR number, or the admin passcode.
