# 🛡️ Access Controls Investigation & Incident Analysis

## 📖 Scenario

You’re the first cybersecurity professional hired by a growing business. Recently, a deposit was made from the business to an unknown bank account. The finance manager says they didn’t make a mistake. Fortunately, they were able to stop the payment. The owner has asked you to investigate what happened to prevent any future incidents.

To do this, you’ll need to do some accounting on the incident to better understand what happened. First, you will review the access log of the incident. Next, you will take notes that can help you identify a possible threat actor. Then, you will spot issues with the access controls that were exploited by the user. Finally, you will recommend mitigations that can improve the business' access controls and reduce the likelihood that this incident reoccurs.

---

## 📄 Access Log Details

- **Event Source:** AdsmEmployeeService
- **Event Category:** None
- **Event ID:** 1227
- **Date:** 10/03/2023
- **Time:** 8:29:57 AM
- **User:** Legal\Administrator
- **Computer:** Up2-NoGud
- **IP:** 152.207.255.255
- **Description:** Payroll event added. FAUX_BANK

---

## 📊 Access Controls Worksheet

| Category | Note(s) | Issue(s) | Recommendation(s) |
| :--- | :--- | :--- | :--- |
| **Authorization / authentication** | - The event took place on 10/03/23.<br>- The user is Legal/Administrator.<br>- The IP address of the computer used to login is 152.207.255.255. | - Robert Taylor Jr is an admin.<br>- His contract ended in 2019, but his account accessed payroll systems in 2023. | - User accounts should expire after 30 days.<br>- Contractors should have limited access to business resources.<br>- Enable MFA. |
