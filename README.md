# DamlReview

DamlReview is a project that allow to request reviews for text documents.

### I. Overview

The so-called 'requesters' can create text documents and then open a review request for them. A review request is assigned to a single reviewer, and only a single request can be opened for a specific document.
A proposer can cancel the review request at any time. A reviewer can make some comments in the review or approve it directly. In the case of a revision, the requester can use ChangeContentAndCancelReviews to edit the document and open a new blank revision. When the document is modified all related revisions are automatically closed. The review and approval process must be done within the limits specified in the review contract. If the limits are exceeded, the audit contract is automatically closed when the audit/approval choice is exercised.

### II. Workflow

The workflow start with a open Document contract:

1. Proposer creates a DocumentReview contract with a certain expire date for a specific reviewer. The new contract created start in OPEN state
2. The reviewer exercises the Review choice and adds the comment "Improve the conclusion" in the review contract. The contract moves into IN_REVIEW state
3. The applicant makes changes to the contract by exercising the ChangeContentAndCancelReviews choice
4. The reviewer finally approves the contract and it goes to APPROVED status

### IV. Compiling & Testing

To compile and test, run the pre-written script in the `Test.daml` under /daml OR run:

```
$ daml start
```

The test environment is setup with some documents and reviews specified in the `Setup.daml`
