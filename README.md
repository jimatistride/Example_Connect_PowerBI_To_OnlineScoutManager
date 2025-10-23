# 🦫 Online Scout Manager Power BI Connectors

**Author:** Jim Walker  
**Role:** BI Consultant & Treasurer — Wyre Forest 17 (Mid Severn) Sea Scouts

## 📖 Overview

This repository provides working Power BI (Power Query M) scripts to connect securely to the Online Scout Manager (OSM) API using OAuth2 client credentials.

These queries were developed to help Scout Group leaders, treasurers, and section admins automate and visualise key data directly in Power BI — including:

- 💰 Section balances and outstanding payments
- 👥 Section sizes and membership summaries
- 🔐 Secure authentication using your own OSM API keys
- 🧭 100% compliant with OSM's API and rate-limit policies

## 🧩 Scripts Included

### 1. OSM_SectionBalances.pq

Retrieves all sections you have access to and totals the amount currently owed from the OSM Online Payments module.

**Outputs:**
| section_id | section_name | section_type | group_name | amount_owing |
|------------|--------------|--------------|------------|--------------|

### 2. OSM_GroupDashboard.pq

Calls OSM's Group Dashboard endpoint to return section sizes and outstanding payments using the latest structure (getGroupDashboard).

**Outputs:**
| section_id | section_name | section_type | group_name | section_size | amount_owing |
|------------|--------------|--------------|------------|--------------|--------------|

## ⚙️ Setup Instructions

### Create an OAuth App in OSM

1. Log in to Online Scout Manager
2. Go to: **Settings → My Account Details → Developer Tools → My Applications**
3. Create a new app and copy your:
   - Client ID
   - Client Secret

### In Power BI Desktop

1. Go to **Get Data → Blank Query**
2. Open the **Advanced Editor**
3. Paste one of the `.pq` scripts
4. Replace the placeholders:
   ```
   ClientId     = "YOUR_CLIENT_ID"
   ClientSecret = "YOUR_CLIENT_SECRET"
   ```
5. When prompted for credentials, choose **Anonymous**  
   (authentication is handled via the script headers)

### Set Data Privacy

- Privacy level: **Organizational** (recommended) or **None** if used locally

### Refresh

- Power BI will now call OSM's API securely
- You can refresh manually or schedule updates in Power BI Service

## 🧠 Notes

- All queries use OAuth2 client credentials flow, meaning no personal login is required
- Please respect OSM's rate limits (queries are lightweight, but avoid frequent refreshes)
- Sensitive data like names or payments should not be shared outside your Group's secure environment

You can easily join these tables in Power BI to build dashboards for:

- Subscription tracking
- Membership trends
- Event attendance summaries
- Section performance

## 🏕️ Why I Built This

 As a BI Consultant in my preofesl life, I wanted to do something which comes easily to me to help other groups.

These scripts aim to make financial and membership reporting simpler, transparent, and reusable for any Group or District using OSM.

## 🤝 Contributing

Contributions are welcome! If you improve a query or adapt it for other OSM endpoints (badges, attendance, events), feel free to open a pull request.

## ⚠️ Disclaimer

These scripts are unofficial and use OSM's public API endpoints as documented in their developer tools.  
Always comply with OSM's terms of service and data protection policies.

## 📬 Contact

**Jim Walker**  
💼 BI Consultant | 💚 Scout Volunteer  
📧 treasurer@midsevernseascouts.org.uk

🌍 **Wyre Forest 17 (Mid Severn) Sea Scouts**