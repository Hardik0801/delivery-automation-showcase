# Demo walkthrough

The Streamlit demo is a simulated environment. No real customer is contacted and no real carrier booking is made.

## Scenario 1: Confirm delivery

- Select sample order **ORDER-101**.
- In the customer simulator, choose **Confirm**.
- The simulated carrier accepts the original slot.
- The dashboard displays the confirmed outcome.

## Scenario 2: Reschedule

- Select **ORDER-102** and request another time.
- Choose one of the offered alternative delivery windows.
- The simulated carrier accepts the selected window.
- The order moves to rescheduled.

## Scenario 3: Reminder and staff escalation

- Leave **ORDER-103** unanswered.
- Advance the demo clock to the reminder time.
- Advance to the review deadline.
- Observe the unresolved delivery in the staff review queue.
- Acknowledge the alert. The order remains in review.

## Scenario 4: Exceptions

- Enable **Simulate carrier rejection** before confirming or booking.
- Alternatively, request another time, advance the demo clock by 16 minutes, and attempt to select an expired offer.
- Review the resulting exception state.

## Scenario 5: Reporting

- Open the dashboard and activity history.
- Export simulated records as CSV or JSON.

## Demo media

The private project includes a 35-second captioned video. A reviewed public copy can be added to this repository later.

**Note:** This documentation intentionally contains no private source code, credentials, or customer records.
