# People Empowering App - User Flows
## Visual User Journey Diagrams

This document contains detailed user flows for the three primary personas based on research findings.

---

## Flow 1: Mr. L's Journey - Emergency Housing Seeker
**Persona:** The Overwhelmed Survivor (35-44, Brooklyn)
**Context:** First-time user in crisis, feeling lost and overwhelmed
**Primary Need:** Simple guidance with human support option
**Key Quote:** "Easy to use, don't make me more confused. Let me chat directly with someone."

### Flow Diagram

```mermaid
flowchart TD
    Start([Mr. L opens app<br/>Feeling overwhelmed]) --> Onboard{First time user?}

    Onboard -->|Yes| Welcome[Welcome Screen<br/>Simple explanation<br/>🎯 FEATURE: Plain language]
    Onboard -->|No| Dashboard

    Welcome --> SituationQ[Quick Situation Assessment<br/>3-4 simple questions<br/>🎯 FEATURE: Proactive suggestions]

    SituationQ --> SitType{What help needed?}
    SitType -->|Emergency housing| Emergency[Emergency Resources<br/>Immediate shelter options<br/>Crisis hotlines visible]
    SitType -->|Permanent housing| Permanent[Housing Search Path]
    SitType -->|Both| Both[Both Paths Available<br/>Emergency prioritized]
    SitType -->|Not sure| Help1[🎯 FEATURE: Human Support<br/>"Chat with someone now"]

    Emergency --> ActionPlan1[🎯 FEATURE: Step-by-Step Action Plan<br/>Emergency Housing Path<br/>━━━━━━━━━━━━━━━━<br/>Step 1: Call DHS now<br/>Step 2: Gather these docs<br/>Step 3: Go to intake center]

    Permanent --> ActionPlan2[🎯 FEATURE: Step-by-Step Action Plan<br/>Permanent Housing Path<br/>━━━━━━━━━━━━━━━━<br/>Step 1: Check eligibility<br/>Step 2: Apply for voucher<br/>Step 3: Find apartment]

    Both --> ActionPlan1

    ActionPlan1 --> Confusion{Confused or<br/>stuck?}
    ActionPlan2 --> Confusion

    Confusion -->|Yes| HumanSupport[🎯 FEATURE: Human Support<br/>━━━━━━━━━━━━━━━━<br/>Options:<br/>• Live Chat<br/>• Phone Call<br/>• Video Call<br/>• Text Message]
    Confusion -->|No, continue| Step1[Complete Step 1<br/>Clear instructions<br/>No jargon]

    HumanSupport --> Connected[Connected to Support<br/>Real person guidance]
    Connected --> Step1

    Step1 --> Progress1[✓ Progress Saved<br/>🎯 FEATURE: Progress tracking<br/>"Great job! Step 1 done"]

    Progress1 --> Documents{Need to upload<br/>documents?}

    Documents -->|Yes| DocHelp[🎯 FEATURE: Document Management<br/>━━━━━━━━━━━━━━━━<br/>• Take photo of document<br/>• View checklist<br/>• Missing docs? Get guidance]
    Documents -->|No| Step2

    DocHelp --> DocConfused{Can't find<br/>document?}
    DocConfused -->|Yes| DocGuidance[Missing Document Help<br/>Where to get it<br/>Alternatives available]
    DocConfused -->|No| DocUpload[Photo Upload<br/>🎯 FEATURE: Accessibility]

    DocGuidance --> HumanSupport2[Option: Ask human<br/>for help]
    DocUpload --> Step2[Continue to Step 2]
    HumanSupport2 --> Step2

    Step2 --> Step3[Complete remaining steps<br/>Always showing:<br/>• Progress bar<br/>• Next action<br/>• Help button]

    Step3 --> Reminder[🎯 FEATURE: Proactive Suggestions<br/>━━━━━━━━━━━━━━━━<br/>Gentle reminder:<br/>"Don't forget your<br/>appointment tomorrow"]

    Reminder --> CommunityTips{Want tips from<br/>others?}

    CommunityTips -->|Yes| Community[🎯 FEATURE: Community Tips<br/>━━━━━━━━━━━━━━━━<br/>"Others say: Bring extra<br/>copies of ID"<br/>✓ Verified by official source]
    CommunityTips -->|No| Dashboard

    Community --> Dashboard[Dashboard<br/>━━━━━━━━━━━━━━━━<br/>• Current progress<br/>• Next steps<br/>• Notifications<br/>• Quick access to human help]

    Dashboard --> CheckProgress{Check<br/>progress}
    CheckProgress -->|Yes| ShowProgress[Progress View<br/>Visual timeline<br/>What's done, what's next]
    CheckProgress -->|No| End

    ShowProgress --> NeedHelp{Need help?}
    NeedHelp -->|Yes| HumanSupport
    NeedHelp -->|No| End([Journey continues...<br/>User feels supported,<br/>not confused])

    style Start fill:#667eea,color:#fff
    style End fill:#28a745,color:#fff
    style HumanSupport fill:#ffc107,color:#000
    style HumanSupport2 fill:#ffc107,color:#000
    style Connected fill:#ffc107,color:#000
    style ActionPlan1 fill:#764ba2,color:#fff
    style ActionPlan2 fill:#764ba2,color:#fff
    style Dashboard fill:#17a2b8,color:#fff
    style Community fill:#17a2b8,color:#fff
```

### Key Design Requirements from Flow 1:
- **Immediate human support access** at every confusion point
- **Progress visibility** throughout journey
- **Document help** integrated into flow
- **Plain language** at every step
- **No dead ends** - always a next action or help option

---

## Flow 2: Ms. Ellis's Journey - Voucher Holder Seeking Housing
**Persona:** The Resourceful Advocate (55-64, Manhattan)
**Context:** Has voucher, tech-savvy, faces landlord discrimination
**Primary Need:** Landlord engagement/credentialing before meetings
**Key Quote:** "Get landlords involved... it would be good if the landlord had the necessary information about you before meeting them."

### Flow Diagram

```mermaid
flowchart TD
    Start([Ms. Ellis opens app<br/>Has voucher, ready to search]) --> Login[Login/Dashboard<br/>Returning user]

    Login --> Profile{Profile<br/>complete?}

    Profile -->|No| CreateProfile[🎯 FEATURE: Landlord Credentialing<br/>━━━━━━━━━━━━━━━━<br/>Create Tenant Profile:<br/>• Employment history<br/>• References<br/>• Voucher details<br/>• Personal statement]
    Profile -->|Yes| Search

    CreateProfile --> Upload[Upload Documents<br/>🎯 FEATURE: Document Management<br/>━━━━━━━━━━━━━━━━<br/>• Photo of voucher<br/>• Proof of income<br/>• References<br/>• ID]

    Upload --> Privacy[🎯 FEATURE: Privacy Protection<br/>━━━━━━━━━━━━━━━━<br/>Control what landlords see:<br/>☑ Employment info<br/>☑ References<br/>☐ Home address<br/>☐ Phone (until approved)]

    Privacy --> ProfileReview[Review Profile<br/>Preview what landlords see]

    ProfileReview --> Verified{Want official<br/>verification?}

    Verified -->|Yes| Verify[Optional: Get Verified Badge<br/>City confirms voucher validity<br/>Increases landlord trust]
    Verified -->|No| Search

    Verify --> Search[Search for Housing<br/>🎯 FEATURE: Filters<br/>━━━━━━━━━━━━━━━━<br/>☑ Accepts vouchers<br/>☐ No broker fee<br/>☐ Wheelchair accessible]

    Search --> Results[Search Results<br/>━━━━━━━━━━━━━━━━<br/>Apartments shown with:<br/>• Landlord ratings<br/>• Voucher acceptance rate<br/>• Response time]

    Results --> SelectApt[Select Apartment<br/>View details]

    SelectApt --> ViewLandlord[View Landlord Info<br/>━━━━━━━━━━━━━━━━<br/>• Past tenant reviews<br/>• Voucher acceptance history<br/>• Response pattern<br/>🎯 FEATURE: Community Tips]

    ViewLandlord --> Decision{Looks good?}

    Decision -->|No| Search
    Decision -->|Yes| ShareProfile[🎯 FEATURE: Landlord Engagement<br/>━━━━━━━━━━━━━━━━<br/>Share Profile with Landlord<br/>━━━━━━━━━━━━━━━━<br/>Before meeting:<br/>✓ Landlord sees credentials<br/>✓ Voucher info explained<br/>✓ References visible<br/>✓ Verified badge shown]

    ShareProfile --> Message[Include Personal Message<br/>━━━━━━━━━━━━━━━━<br/>"I'm a disabled mother<br/>with 16yo son, stable<br/>employment, excellent<br/>references..."<br/>🎯 FEATURE: Voice-to-text option]

    Message --> Send[Send Inquiry<br/>Profile + Message sent]

    Send --> Wait[Waiting for Response<br/>━━━━━━━━━━━━━━━━<br/>Expected response: 24-48hrs<br/>🎯 FEATURE: Proactive notification]

    Wait --> Response{Landlord<br/>response?}

    Response -->|Positive| Schedule[Schedule Viewing<br/>In-app scheduling<br/>Address shared after confirmation]
    Response -->|Negative| Feedback[Landlord declined<br/>━━━━━━━━━━━━━━━━<br/>Required: Reason selection<br/>• Unit filled<br/>• Other applicant selected<br/>• Does not accept vouchers ⚠]
    Response -->|No response 48hrs| Reminder[Auto-reminder sent<br/>to landlord]

    Feedback --> Report{Discriminatory?}
    Report -->|Yes| ReportDiscrim[Report to City<br/>🎯 FEATURE: Advocacy<br/>Aggregate data on discrimination]
    Report -->|No| Search

    ReportDiscrim --> Support[Option: Legal support<br/>🎯 FEATURE: Human Support<br/>Connect to tenant rights org]

    Support --> Search
    Reminder --> Response

    Schedule --> PrepMeeting[🎯 FEATURE: Action Plan<br/>Meeting Preparation<br/>━━━━━━━━━━━━━━━━<br/>Step 1: Print documents<br/>Step 2: Prepare questions<br/>Step 3: Review lease terms]

    PrepMeeting --> CommunityTips[🎯 FEATURE: Community Tips<br/>━━━━━━━━━━━━━━━━<br/>"Others meeting this landlord say:<br/>• Bring extra ID copies<br/>• Ask about utilities<br/>• They're friendly!"<br/>✓ Verified tips]

    CommunityTips --> Meeting[Attend Viewing<br/>Landlord already knows<br/>your background]

    Meeting --> AfterMeeting{How did<br/>it go?}

    AfterMeeting -->|Good| Apply[Submit Application<br/>Through app]
    AfterMeeting -->|Bad| RateLandlord[Rate Experience<br/>Help future voucher holders]
    AfterMeeting -->|Discriminated| ReportDiscrim

    RateLandlord --> Search

    Apply --> Track[Track Application<br/>Status updates]

    Track --> Success{Accepted?}

    Success -->|Yes| Celebrate[🎉 Housing Secured!<br/>━━━━━━━━━━━━━━━━<br/>Next: Moving checklist<br/>🎯 FEATURE: Proactive suggestions]
    Success -->|No| RateLandlord

    Celebrate --> PayItForward[Optional: Share Your Story<br/>Help others learn<br/>🎯 FEATURE: Community building]

    PayItForward --> End([Journey complete<br/>Dignity maintained<br/>Discrimination reduced])

    style Start fill:#667eea,color:#fff
    style End fill:#28a745,color:#fff
    style Celebrate fill:#28a745,color:#fff
    style ShareProfile fill:#764ba2,color:#fff
    style CreateProfile fill:#764ba2,color:#fff
    style ReportDiscrim fill:#dc3545,color:#fff
    style Privacy fill:#ffc107,color:#000
    style Verified fill:#17a2b8,color:#fff
```

### Key Design Requirements from Flow 2:
- **Landlord credentialing system** - core differentiator
- **Privacy controls** - user decides what to share
- **Verification badge** - builds trust
- **Discrimination reporting** - advocacy function
- **Community ratings** - landlord accountability
- **Pre-meeting information sharing** - reduces bias

---

## Flow 3: Mr. Patterson's Journey - No-Fee Apartment Search
**Persona:** The Frustrated Renter (35-44, Brooklyn)
**Context:** Professional, tech-savvy, wants to avoid broker fees
**Primary Need:** Direct landlord connection, cost transparency
**Key Quote:** "If this app could help tenants avoid being subject to large broker fees and connect them with landlords."

### Flow Diagram

```mermaid
flowchart TD
    Start([Mr. Patterson opens app<br/>Looking for efficiency]) --> Login{Has<br/>account?}

    Login -->|No| QuickSignup[Quick Signup<br/>Email + Password<br/>Professional expects speed]
    Login -->|Yes| Dashboard

    QuickSignup --> Dashboard[Dashboard<br/>Clean, professional interface]

    Dashboard --> Search[🎯 FEATURE: Advanced Search<br/>━━━━━━━━━━━━━━━━<br/>Filters:<br/>☑ No broker fee ONLY<br/>• Location: Brooklyn<br/>• Price: $2500-3500<br/>• Bedrooms: 1-2]

    Search --> Results[Search Results<br/>━━━━━━━━━━━━━━━━<br/>Sorted by:<br/>• No-fee first (priority)<br/>• Total move-in cost<br/>• Landlord response time]

    Results --> CostCalc[🎯 FEATURE: Cost Calculator<br/>━━━━━━━━━━━━━━━━<br/>Apartment A: $3200/mo<br/>• First month: $3200<br/>• Security: $3200<br/>• Broker fee: $4800 ❌<br/>━━━━━━━━━━━━━━━━<br/>Total: $11,200<br/>vs<br/>Apartment B: $3400/mo (no fee)<br/>Total: $6,800 ✓ SAVES $4,400]

    CostCalc --> SelectApt[Select No-Fee Apartment<br/>View full details]

    SelectApt --> VerifyNoFee[Verify No-Fee Status<br/>━━━━━━━━━━━━━━━━<br/>✓ Landlord verified<br/>✓ No hidden fees<br/>🎯 FEATURE: Transparency]

    VerifyNoFee --> ViewLandlord[View Landlord Profile<br/>━━━━━━━━━━━━━━━━<br/>• Response time: 4 hours avg<br/>• Rating: 4.5/5<br/>• Reviews from tenants<br/>• Building violations: None]

    ViewLandlord --> CommunityCheck{Check<br/>community tips?}

    CommunityCheck -->|Yes| Community[🎯 FEATURE: Community Tips<br/>━━━━━━━━━━━━━━━━<br/>"Recent renters say:<br/>• Landlord responsive<br/>• Building well-maintained<br/>• Ask about utilities cost"<br/>✓ Verified]
    CommunityCheck -->|No| Contact

    Community --> Contact[🎯 FEATURE: Direct Landlord Contact<br/>━━━━━━━━━━━━━━━━<br/>Contact Options:<br/>• Message through app<br/>• Schedule viewing<br/>• Request more info<br/>NO BROKER MIDDLEMAN]

    Contact --> Message[Send Message<br/>Professional template available<br/>or write custom]

    Message --> Sent[Message Sent<br/>━━━━━━━━━━━━━━━━<br/>🎯 FEATURE: Email integration<br/>Copy sent to his email]

    Sent --> Response{Landlord<br/>responds?}

    Response -->|Within 24hrs| Schedule[Schedule Viewing<br/>Direct calendar integration<br/>Professional expects efficiency]
    Response -->|No response| Reminder[Auto-reminder after 48hrs<br/>If still no response:<br/>Flag as unresponsive]

    Reminder --> Response

    Schedule --> DocPrep[🎯 FEATURE: Document Management<br/>━━━━━━━━━━━━━━━━<br/>Prepare Application Docs:<br/>☑ Proof of income<br/>☑ Credit report<br/>☑ References<br/>☑ ID<br/>━━━━━━━━━━━━━━━━<br/>Save as template for future]

    DocPrep --> Upload[Upload Documents<br/>🎯 FEATURE: Photo upload<br/>All docs in one place]

    Upload --> Viewing[Attend Viewing<br/>Professional interaction]

    Viewing --> Decision{Want to<br/>apply?}

    Decision -->|No| Rate[Rate Experience<br/>Help other renters]
    Decision -->|Yes| Apply[🎯 FEATURE: Streamlined Application<br/>━━━━━━━━━━━━━━━━<br/>Apply Directly to Landlord<br/>━━━━━━━━━━━━━━━━<br/>• All docs pre-uploaded<br/>• Digital signature<br/>• Instant submission<br/>NO BROKER FEES]

    Rate --> Search

    Apply --> Confirmation[Application Submitted<br/>━━━━━━━━━━━━━━━━<br/>Expected response: 3-5 days<br/>🎯 FEATURE: Email notifications<br/>Track status in app]

    Confirmation --> Track[Track Application<br/>Dashboard shows status]

    Track --> LandlordReview{Landlord<br/>decision?}

    LandlordReview -->|Approved| Success[🎉 Application Approved!<br/>━━━━━━━━━━━━━━━━<br/>Next steps:<br/>• Review lease<br/>• Schedule signing<br/>• Arrange move-in]
    LandlordReview -->|Denied| Feedback[Feedback from landlord<br/>Optional: Ask why]
    LandlordReview -->|Pending| Wait[Waiting...]

    Wait --> Track
    Feedback --> Search

    Success --> LeaseReview[Review Lease Terms<br/>━━━━━━━━━━━━━━━━<br/>🎯 FEATURE: Lease checker<br/>Highlights unusual terms<br/>Option: Legal review]

    LeaseReview --> Questions{Questions about<br/>lease?}

    Questions -->|Yes| HumanHelp[🎯 FEATURE: Human Support<br/>━━━━━━━━━━━━━━━━<br/>Options:<br/>• Chat with housing counselor<br/>• Tenant rights lawyer<br/>• FAQ database]
    Questions -->|No| Sign

    HumanHelp --> Sign[Digital Lease Signing<br/>Secure e-signature]

    Sign --> Payment[First Month + Security<br/>━━━━━━━━━━━━━━━━<br/>Total: $6,800<br/>SAVED: $4,400 in broker fees ✓]

    Payment --> MovingChecklist[🎯 FEATURE: Proactive Suggestions<br/>━━━━━━━━━━━━━━━━<br/>Moving Checklist:<br/>• Transfer utilities<br/>• Update address<br/>• Schedule movers<br/>• Renter's insurance]

    MovingChecklist --> Recommend{Satisfied with<br/>experience?}

    Recommend -->|Yes| Share[Share App with Colleagues<br/>Professional network referral<br/>🎯 Word-of-mouth growth]
    Recommend -->|Maybe| Later[Maybe recommend later<br/>Want to see long-term value]

    Share --> End([Journey complete<br/>$4,400 saved<br/>Efficient process<br/>Professional satisfied])
    Later --> End

    style Start fill:#667eea,color:#fff
    style End fill:#28a745,color:#fff
    style Success fill:#28a745,color:#fff
    style Payment fill:#28a745,color:#fff
    style CostCalc fill:#764ba2,color:#fff
    style Apply fill:#764ba2,color:#fff
    style Contact fill:#17a2b8,color:#fff
    style VerifyNoFee fill:#17a2b8,color:#fff
```

### Key Design Requirements from Flow 3:
- **No-fee filter prominent** - top priority feature
- **Cost calculator** - total move-in cost transparency
- **Direct landlord messaging** - bypass brokers entirely
- **Professional UI/UX** - clean, efficient, fast
- **Email integration** - his preferred channel
- **Document templates** - reusable for efficiency
- **Verification system** - prevent fee bait-and-switch

---

## Cross-Flow Feature Integration

### Features Used Across All 3 Flows:

| Feature | Mr. L | Ms. Ellis | Mr. Patterson | Priority |
|---------|-------|-----------|---------------|----------|
| **Step-by-Step Action Plans** | ✓✓✓ Critical | ✓✓ Important | ✓ Moderate | **TIER 1** |
| **Human Support** | ✓✓✓ Critical | ✓✓ Important | ✓ Backup | **TIER 1** |
| **Proactive Suggestions** | ✓✓✓ Critical | ✓✓ Important | ✓✓ Important | **TIER 1** |
| **Document Management** | ✓✓✓ Critical | ✓✓ Important | ✓✓ Important | **TIER 1** |
| **Community Tips + Verification** | ✓✓ Important | ✓✓✓ Critical | ✓ Moderate | **TIER 2** |
| **Landlord Engagement/Credentialing** | - | ✓✓✓ Critical | ✓✓ Important | **TIER 2** |
| **Direct Landlord Contact** | ✓ Moderate | ✓✓✓ Critical | ✓✓✓ Critical | **TIER 2** |
| **No-Fee Filter** | - | - | ✓✓✓ Critical | **TIER 2** |
| **Privacy Protection** | ✓✓ Important | ✓✓✓ Critical | ✓ Moderate | **TIER 1** |
| **Progress Tracking** | ✓✓✓ Critical | ✓✓ Important | ✓✓ Important | **TIER 1** |

### Universal Screens Needed (All Flows):
1. **Onboarding/Welcome** - First-time user experience
2. **Dashboard** - Home base showing progress, notifications, quick actions
3. **Search/Browse** - Find housing resources or listings
4. **Action Plan View** - Step-by-step guidance interface
5. **Document Manager** - Upload, store, organize documents
6. **Human Support Hub** - Chat, call, video, text options
7. **Profile/Settings** - User account management
8. **Notifications** - Reminders, updates, proactive suggestions

### Unique Screens by Flow:
- **Mr. L:** Emergency resources, simplified intake assessment
- **Ms. Ellis:** Landlord credentialing, discrimination reporting, verification badge
- **Mr. Patterson:** Cost calculator, no-fee filter, professional application template

---

## Next Steps: Wireframing Priority

Based on these flows, here's the **recommended wireframing order**:

### Phase 1: Core Screens (Week 1)
1. **Dashboard** - Used by all 3 personas
2. **Action Plan View** - 100% validation, highest value
3. **Human Support Hub** - 100% want this option
4. **Onboarding Flow** - Critical first impression

### Phase 2: Search & Discovery (Week 2)
5. **Search/Filter Interface** - All flows need this
6. **Search Results** - Listings display
7. **Detail View** - Apartment/resource details
8. **Document Manager** - Universal need

### Phase 3: Differentiating Features (Week 3)
9. **Landlord Credentialing** - Ms. Ellis's critical need
10. **Cost Calculator** - Mr. Patterson's value prop
11. **Community Tips Interface** - Verification mechanism
12. **Emergency Resources** - Mr. L's immediate need

### Phase 4: Supporting Features (Week 4)
13. **Profile/Settings**
14. **Notifications Center**
15. **Help/FAQ**
16. **Legal/Reporting Interface**

---

## Design Handoff Package

When these flows are approved, the design team needs:

✅ **User flows (this document)** - Journey maps
✅ **Feature requirements** - From research findings
✅ **Personas** - Mr. L, Ms. Ellis, Mr. Patterson
⬜ **Wireframes** - Low-fidelity screens (NEXT)
⬜ **Content requirements** - Copy, messaging, tone
⬜ **Interaction patterns** - Gestures, animations
⬜ **Accessibility specs** - Voice, photo, text modes
⬜ **Technical constraints** - Platform, APIs, integrations

---

## Questions for Validation

Before moving to wireframes, confirm:

1. **Do these flows accurately represent your research findings?**
2. **Are there any critical decision points missing?**
3. **Should we add flows for edge cases** (e.g., application denied, discrimination encountered)?
4. **Which flow should we prototype first?** (Recommend: Mr. L - highest need)
5. **Do we need additional personas/flows?** (e.g., caseworker helping client?)

---

## Measurement & Success Metrics

How we'll know these flows work:

### Mr. L Flow Success:
- Time to first action plan: < 2 minutes
- Confusion rate: < 10% (need human help)
- Completion rate: > 80% (finish first step)
- User quote target: "This didn't make me more confused"

### Ms. Ellis Flow Success:
- Profile completion rate: > 90%
- Landlord response rate: > 60%
- Discrimination reports: Decrease over time (system working)
- Voucher acceptance rate: Increase

### Mr. Patterson Flow Success:
- No-fee filter usage: > 90% (primary value)
- Time to application: < 15 minutes
- Broker fee savings: $3,000-7,000 per user
- Recommendation rate: Neutral → Somewhat likely → Very likely

---

**Document Version:** 1.0
**Last Updated:** October 2025
**Status:** Ready for wireframing

