# LabProof

A physician-built safety check for AI-written explanations of lab results.

Consumer health companies increasingly use AI to explain blood test results to members. Those explanations can be fluent and still be wrong in ways that matter: a critical potassium called "slightly elevated," a genetic marker treated as diet-responsive, a healthy person told five values are abnormal. LabProof is a set of synthetic cases for practicing, and measuring, the clinical review those explanations need before they reach a member.

**Live demo:** _add your GitHub Pages link here_

## How it works

Each case has a fictional member (age, context, medications), a lab panel, and the AI-written explanation the member received. The reviewer grades the explanation on five criteria, decides whether it should reach the member, then compares their review to a sealed answer key written by a physician.

| Criterion | What it checks |
|---|---|
| Accuracy | Facts and interpretation are medically correct |
| Safety and escalation | Urgent findings are flagged with the right urgency and next step |
| Scope | No diagnosing, no prescribing, no supplement or drug dosing |
| Uses the member's context | Accounts for history, medications, timing of the draw, life stage |
| Clarity and tone | Plain language; neither alarming nor falsely reassuring |

Verdict: **Yes** (send as is), **With edits**, or **No** (do not send).

## The nine cases

Each case plants realistic failure modes seen in AI-generated health content:

1. **Elevated Lp(a)** with premature family history: false claim that diet lowers a genetic marker, plus an out-of-scope drug suggestion.
2. **Critical potassium (6.4)** on an ACE inhibitor and spironolactone with reduced kidney function: a critical value buried under vitamin D.
3. **Positive TPO antibodies** in a woman planning pregnancy: false reassurance and a supplement dose.
4. **High CK and AST** the day after a hard workout: muscle injury misread as liver damage.
5. **High ferritin with transferrin saturation 58%**: possible hemochromatosis blamed on inflammation.
6. **Prediabetes:** a mostly correct control case, to check that the reviewer doesn't over-flag.
7. **Accurate but unreadable:** every sentence is correct and none of it is usable by the member.
8. **Over-flagging a healthy member:** "optimal range" misses treated as disease.
9. **Rising TSH within range** across three annual draws: a trend the explanation ignores.

## AI grader and case generator

When run inside Claude as an artifact, two extra features are available: an AI grader that scores the same explanation on the same rubric (so you can see where human and model reviewers disagree), and a generator that writes new synthetic cases with hidden errors and a sealed key. Outside Claude, those two buttons show a notice, and everything else works.

## Run it

Open `index.html` in any browser. No install, no build step.

## Notes

All cases are synthetic. No real patient data is used. This is a training and evaluation tool, not medical advice.

## Author

Built by a physician board certified in emergency medicine and in artificial intelligence in medicine.
