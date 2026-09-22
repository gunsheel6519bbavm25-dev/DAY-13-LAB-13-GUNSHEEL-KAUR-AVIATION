# DAY-13-LAB-13-GUNSHEEL-KAUR-AVIATION
Day 13 Generative AI lab on Retrieval-Augmented Generation, source verification, grounded answers, citation quality, risk auditing and human review in aviation.

Programme: BBA Aviation Management
Course: Generative AI for Business
Student: Gunsheel Kaur
Roll Number: 2520996519
Lab: Day 13 — RAG and Source Verification

1. Objective

The objective of this lab is to understand Retrieval-Augmented Generation (RAG) and evaluate how source-grounded AI responses differ from ungrounded responses.

The lab focuses on:

Retrieval-Augmented Generation
Document-grounded answers
Source verification
Claim–source matching
Citation quality
Missing-information handling
Context preservation
Risk auditing
Human verification
2. Understanding Retrieval-Augmented Generation

Retrieval-Augmented Generation (RAG) is an approach in which an AI system first retrieves relevant information from a supplied source and then uses that information to generate an answer.

RAG Workflow

User Question
↓
Relevant Source Information Retrieved
↓
Retrieved Information Added to AI Context
↓
AI Generates Grounded Answer
↓
Human Verifies Answer and Source

RAG can improve grounding because the AI has access to a specific source. However, it does not automatically guarantee that the answer is completely correct, current, complete or suitable for business use.

3. Normal Chatbot vs RAG Chatbot
Normal Chatbot	RAG / Document-Grounded Chatbot
Uses general model knowledge and prompt context	Uses information from a supplied document
May not know an organisation's specific policy	Can retrieve relevant policy information
May generate plausible but unsupported information	More likely to provide source-based information
May not provide precise citations	Can provide page, section or passage references
Can answer confidently without the actual policy	Can acknowledge when information is not found in the source
Requires human verification	Still requires human verification
4. Selected Source Document

A fictional instructor-approved airline baggage policy was used for demonstration and learning purposes.

Source Details

Document Title: AeroVista Airlines Checked Baggage Handling Policy

Issuing Organisation: AeroVista Airlines

Revision Date: 1 August 2026

Document Purpose: To explain the procedure and conditions relating to delayed checked baggage.

Intended Audience: Passengers and customer-service staff

Number of Pages: 3

Main Topics Covered
Reporting delayed baggage
Baggage tracing
Delivery arrangements
Reasonable expense reimbursement
Compensation conditions
Exceptions and limitations
Information Not Covered

The document does not provide:

A guaranteed delivery time in every case
A fixed compensation amount for every passenger
Passenger-specific reimbursement decisions
Individual booking information

The document was treated as the current version for this classroom exercise and was approved for upload because it is fictional and contains no real passenger or confidential information.

5. Ungrounded Question and Answer
Question

According to the airline's policy, what assistance is provided when checked baggage is delayed? Include the reporting procedure, delivery timeline, expense reimbursement and compensation conditions.

Ungrounded Answer

A typical airline baggage policy may require passengers to report delayed baggage at the baggage service desk and complete a baggage irregularity report. The airline may trace the baggage and arrange delivery to the passenger once it is located. Delivery may commonly take between 24 and 72 hours depending on the circumstances. Reasonable essential expenses may sometimes be reimbursed, subject to receipts and policy limits. Compensation may depend on the applicable airline rules and the circumstances of the delay.

Observation

This answer sounds plausible but is not actually based on the selected policy because the document had not been supplied to the AI.

6. Ungrounded Answer Audit
Claim	Evidence Available?	Status	Risk
Passenger should report delayed baggage at the baggage service desk	No	Unsupported	Medium
Passenger may need to complete a baggage irregularity report	No	Unsupported	Medium
Delivery may take 24–72 hours	No	Unsupported	High
Essential expenses may be reimbursed	No	Unsupported before source review	High
Compensation depends on applicable rules	No	Unsupported before source review	Medium
Airline may trace and arrange delivery	No	Unsupported before source review	Medium
Key Finding

The ungrounded answer contained plausible general information but could not be treated as the airline's actual policy.

The biggest risk was the invented 24–72 hour delivery timeline, because a passenger could incorrectly treat it as a guaranteed policy commitment.

7. Grounding Instructions

After uploading the approved source, the following grounding instruction was provided:

Use only the uploaded document to answer my questions. Do not use general knowledge to fill missing information. For every factual claim, provide the relevant page number, section heading or source passage. If the information is not available in the document, state: “Not found in the supplied document.”

This instruction helps prevent the AI from filling gaps with unsupported information.

8. Grounded Question and Answer
Question

According to the uploaded policy document, what assistance is provided when checked baggage is delayed? Include the reporting procedure, delivery timeline, expense reimbursement and compensation conditions. Use only the supplied document and cite the relevant section or page for every claim.

Grounded Answer

According to the supplied AeroVista Airlines Checked Baggage Handling Policy:

Passengers should report delayed checked baggage to the baggage-service desk and provide the required travel and baggage details. [Page 1, Section 2: Reporting Delayed Baggage]
The airline will initiate a baggage-tracing process after the delay is reported. [Page 1, Section 3: Baggage Tracing]
Delivery arrangements depend on when the baggage is located and operational circumstances. The policy does not guarantee a fixed delivery time for every case. [Page 2, Section 4: Delivery Arrangements]
Reasonable essential expenses may be considered where the policy conditions are met and appropriate supporting receipts are provided. [Page 2, Section 5: Essential Expenses]
Compensation is subject to the conditions and limitations stated in the policy. The document does not provide one fixed compensation amount applicable to every passenger. [Page 3, Section 6: Compensation Conditions]

Therefore, a specific guaranteed delivery time or universal compensation amount is not found in the supplied document.

9. Ungrounded vs Grounded Comparison
Evaluation Criterion	Ungrounded Answer	Grounded Answer
Source document used	No	Yes
Claims supported by evidence	No	Yes
Citations provided	No	Yes
Policy details invented	Yes	No
Missing information acknowledged	No	Yes
Confidence appropriate to evidence	No	Yes
Suitable for business use	Not without verification	More suitable after human verification
Human verification required	Yes	Yes
Conclusion

The grounded answer is more useful for policy-related work because it uses the supplied source and clearly identifies information that is not available.

However, human verification remains necessary.

10. Five-Step Verification Routine

The verification routine used in this lab was:

Claim → Source → Match → Context → Action

Examples
Claim	Source	Match	Context Preserved?	Action
Delayed baggage should be reported at the baggage-service desk	Page 1, Section 2	Yes	Yes	Accept
Airline starts baggage tracing after reporting	Page 1, Section 3	Yes	Yes	Accept
Delivery is guaranteed within 24–72 hours	No supporting source	No	No	Reject
Essential expenses may be considered subject to policy conditions	Page 2, Section 5	Yes	Yes	Accept
One fixed compensation amount applies to every passenger	Page 3, Section 6	No	No	Reject
Key Principle

A claim should not be accepted merely because it sounds realistic. It must match the actual source and preserve its conditions and limitations.

11. Citation Quality Check

A citation should be checked against the exact claim it is attached to.

AI Claim	Citation	Supports Claim?	Correction
Delayed baggage must be reported at the baggage-service desk	Page 1, Section 2	Yes	No correction
Baggage tracing starts after reporting	Page 1, Section 3	Yes	No correction
Delivery is guaranteed within 24 hours	Page 2, Section 4	No	Remove guarantee and state that no fixed time is provided
Essential expenses may be considered	Page 2, Section 5	Yes	Retain conditions
Fixed compensation is provided to every passenger	Page 3, Section 6	No	State that compensation depends on policy conditions
Citation Principle

Merely adding a page number does not make an unsupported statement reliable. The citation must actually support the claim.

12. Missing-Information Test
Test Question

What compensation amount will every passenger receive if delayed baggage is not delivered within 12 hours?

Result

The supplied document does not provide:

A universal compensation amount
A guaranteed compensation trigger after 12 hours

Therefore, the AI should not invent a compensation amount.

The appropriate response is to state that the information is not specified in the supplied document and further verification may be required.

13. Conditional Information Test
Question

Does the policy guarantee baggage delivery within a fixed number of hours in every situation?

Source Finding

The policy states that delivery arrangements depend on when baggage is located and operational circumstances. It does not provide a fixed delivery guarantee for every case.

AI Interpretation

The AI should state that baggage delivery is not guaranteed within a fixed number of hours and depends on the circumstances described in the policy.

Key Learning

The conditional nature of a source statement must be preserved. A conditional policy statement should not be converted into an unrealistic guarantee.

14. Grounded Passenger Response

Dear Passenger,

We understand that delayed baggage can be inconvenient. According to the supplied baggage policy, delayed checked baggage should be reported at the baggage-service desk with the required travel and baggage details. The airline can then begin the baggage-tracing process.

Delivery arrangements depend on when the baggage is located and operational circumstances; the policy does not guarantee a fixed delivery time for every case. Reasonable essential expenses may be considered when the applicable policy conditions are met and supporting receipts are provided. Compensation is subject to the conditions and limitations in the policy.

Internal references: Pages 1–3, Sections 2–6.

If a specific compensation amount or delivery commitment is required, [VERIFY AIRLINE POLICY].

Review
Accuracy: Supported by supplied policy
Tone: Professional and empathetic
Compliance: No unsupported promise
Context: Conditions retained
Citation quality: Relevant sections identified
Privacy: No passenger information included
Appropriate uncertainty: Yes
15. Second RAG Scenario — Flight Cancellation Policy

A fictional AeroVista cancellation policy was used for the second scenario.

Question Before Uploading

According to AeroVista's cancellation policy, what refund will a passenger receive after an airline-initiated cancellation?

Ungrounded Answer

An airline may offer a full refund, alternative flight or travel credit when a flight is cancelled. The exact option may depend on the airline's terms and the passenger's ticket type.

Observation

The answer provides general possibilities but does not establish what the fictional airline's actual policy says.

Grounded Question

Using only the uploaded cancellation policy, what options are available when the airline cancels a flight? Cite the relevant section and do not add information not contained in the document.

Grounded Answer

The supplied cancellation policy states that passengers affected by an airline-initiated cancellation may be offered the options specifically described in the policy. The applicable option depends on the circumstances and conditions stated in the document.

[Section 3: Airline-Initiated Cancellation]

If a particular refund amount, travel-credit value or rebooking condition is not stated in the supplied document, it should be marked:

[VERIFY AIRLINE POLICY]

16. Second Scenario Verification

Claim: Airline-initiated cancellation provides options described in the policy.

Source: Section 3

Match: Yes

Context: Conditions retained

Action: Accept, subject to human verification

17. RAG Limitations

RAG can still produce weak or incorrect answers when:

The source document is outdated
The wrong document is uploaded
Relevant information is missing
The document is poorly scanned
Text extraction is incorrect
The system retrieves an irrelevant section
The source itself contains an error
The AI misunderstands the retrieved passage
A citation is attached to the wrong claim
Important conditions are omitted
Important Principle

RAG improves access to source information; it does not make an unreliable source reliable.

18. RAG Risk Audit
Risk	Present?	Evidence	Mitigation
Outdated source	No	Source has a stated revision date	Check revision date before use
Unauthorised document	No	Fictional approved document used	Use only authorised sources
Missing information	Yes	Compensation amount not specified	Mark as [VERIFY AIRLINE POLICY]
Incorrect retrieval	No	Relevant sections retrieved	Check retrieved section
Weak citation	No	Citations checked manually	Match each citation to its claim
Lost context	Possible	Conditions may be omitted by AI	Read surrounding source text
Unsupported claim	Yes	24–72 hour timeline was unsupported	Reject unsupported claim
Sensitive information	No	No passenger data used	Continue using non-sensitive material
Excessive confidence	Yes	General information sounded policy-specific	Use evidence-based language
Missing human approval	Possible	AI output alone is insufficient	Require human review before business use
19. Student Reflection
1. What is Retrieval-Augmented Generation?

Retrieval-Augmented Generation is a method in which AI retrieves relevant information from a supplied source and uses it to generate a more source-grounded answer.

2. What is the difference between an ungrounded and grounded answer?

An ungrounded answer is produced without access to the specific source document, while a grounded answer uses information retrieved from the supplied document.

3. Did the AI invent information before the document was uploaded?

Yes. The ungrounded answer introduced a possible 24–72 hour delivery timeline without evidence from the actual policy.

4. Did the grounded answer contain valid citations?

Yes. The grounded answer used page and section references that matched the claims in the supplied policy.

5. What does “claim–source match” mean?

Claim–source match means checking whether the exact information stated by the AI is actually supported by the cited source.

6. Why must the context surrounding a claim be checked?

Context is important because conditions, exceptions and limitations can change the meaning of a statement. Removing them may turn a conditional policy into a false guarantee.

7. What happened when you asked a question not covered by the document?

The appropriate response was to state that the information was not found in the supplied document instead of inventing an answer.

8. Why does RAG not guarantee truth?

RAG depends on the quality and completeness of the source. If the source is outdated, incorrect or incomplete, the grounded answer can also be incorrect or incomplete.

9. When should an answer be escalated to an authorised person?

An answer should be escalated when the information is missing, unclear, high-risk, operationally important or requires an official policy decision.

10. How could RAG support aviation-management work?

RAG could help aviation managers retrieve information from approved policies, procedures, passenger-service documents and operational guidelines while making it easier to verify claims against the original source.

20. Key Learnings

This lab demonstrated that:

RAG retrieves information from a supplied source before generating an answer.
Grounded answers are more closely connected to the selected source.
Ungrounded AI responses can contain plausible but unsupported information.
Every important claim should be checked against its source.
Citations must actually support the claims they accompany.
Conditions and limitations must be preserved.
Missing information should be acknowledged instead of invented.
RAG does not guarantee that the source itself is correct.
High-risk aviation information requires appropriate human review.
Human verification remains essential before business use.
21. AI Usage Declaration

Generative AI tools were used to assist with the RAG activity, question-answer generation, comparison, source verification and reflection.

The responses were reviewed against the supplied source document, unsupported information was identified, citations were checked and human verification requirements were documented.

22. Final Submission Checklist

RAG concept explained

RAG workflow documented

Normal chatbot vs RAG comparison completed

Source document reviewed

Ungrounded answer generated

Ungrounded answer audited

Grounding instructions applied

Grounded answer generated

Ungrounded vs grounded comparison completed

Five-step verification routine completed

Citation quality checked

Missing-information test completed

Conditional-information test completed

Grounded passenger response created

Second RAG scenario completed

RAG limitations identified

RAG risk audit completed

Student reflection completed

Upload final lab materials to GitHub

23. Suggested GitHub Repository Structure
DAY-13-LAB-13-GUNSHEEL-KAUR-AVIATION/
│
├── README.md
├── LAB13-GUNSHEEL-KAUR-2520996519-AVIATION.docx
│
├── source-documents/
│   ├── aerovista-checked-baggage-policy.pdf
│   └── aerovista-cancellation-policy.pdf
│
└── verification/
    └── rag-source-verification.md
24. Conclusion

This lab demonstrated the difference between ungrounded and document-grounded AI responses through a Retrieval-Augmented Generation workflow.

The activity showed that using a supplied source can improve grounding, citation quality and policy-specific responses. It also demonstrated that AI may introduce plausible information that is not supported by the source when the source is unavailable.

The Claim → Source → Match → Context → Action routine provides a structured method for checking AI-generated claims.

RAG should therefore be treated as a method for improving access to source information rather than a guarantee of truth. Human verification remains essential, especially for operational, policy-sensitive and high-risk aviation information.
