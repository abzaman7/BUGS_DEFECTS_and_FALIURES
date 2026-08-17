# Bugs, Defects, and Failures

Software testing involves more than simply finding "bugs." To understand how software fails and how defects are introduced, it is important to distinguish between **errors, defects, and failures**.

This document explains these concepts, their relationship, common causes, and the **Bug Life Cycle**.

---

## 🐞 What Is a Bug?

A **bug** is an error, flaw, mistake, fault, or defect in software that causes the application to behave differently from what was intended.

In simple terms:

> When the **actual result** does not match the **expected result** defined by the requirements or specifications, it may be considered a bug.

### Example

Suppose a requirement states:

```text
Expected Result:
A user enters valid credentials and is successfully logged in.
```

During testing, the user enters valid credentials but remains on the login page.

```text
Expected Result → User is logged in
Actual Result   → User remains on login page
```

This mismatch indicates a potential **defect/bug**.

---

## 🔍 Error, Defect, and Failure

The terms **error, defect, and failure** are closely related, but they describe different stages of a problem.

### 1. Error

An **error** is a human mistake made during software development or other activities.

It can occur while:

* Understanding requirements
* Designing the system
* Writing code
* Creating test cases
* Configuring the environment
* Communicating with stakeholders

**Example:**

A developer misunderstands a requirement and assumes that a discount should be calculated as `10` instead of `10%`.

This misunderstanding is an **error**.

---

### 2. Defect

A **defect** is introduced into a software work product as a result of an error.

It may exist in:

* Source code
* Requirements
* Design documents
* Test cases
* Configuration
* Other project artifacts

**Example:**

Because the developer misunderstood the discount requirement, the application contains incorrect discount logic.

That incorrect logic is a **defect**.

---

### 3. Failure

A **failure** occurs when the software executes a defect and produces an incorrect or unexpected result.

**Example:**

A customer purchases an item for $100 with a required 10% discount.

```text
Expected Result → $90
Actual Result   → $100
```

If the incorrect discount logic is executed and produces the wrong result, the user experiences a **failure**.

---

## 🔗 Relationship Between Error, Defect, and Failure

The relationship can be summarized as:

```text
Human Error
     ↓
Defect Introduced
     ↓
Defect Is Executed
     ↓
Failure Occurs
```

However, **a defect does not always result in a failure**.

A defect may remain hidden if the specific conditions required to trigger it never occur.

### Example

Imagine an application contains a defect that only occurs when:

* A specific feature is enabled
* A particular input is provided
* A specific browser is used
* A particular sequence of actions is followed

If those conditions never occur, the defect may exist in the software without causing an observable failure.

---

## 🧩 Error → Defect → Failure Example

Consider an online shopping application.

### Step 1: Error

A developer misunderstands the requirement:

> "Free shipping should apply to orders above $50."

The developer interprets it as:

> "Free shipping should apply to orders of $50 or more."

### Step 2: Defect

The developer implements:

```text
Order Amount >= $50 → Free Shipping
```

instead of:

```text
Order Amount > $50 → Free Shipping
```

### Step 3: Failure

A customer places an order worth exactly $50.

```text
Expected → Shipping fee is charged
Actual   → Free shipping is applied
```

The incorrect behavior observed by the customer is a **failure** caused by the underlying **defect**, which originated from a human **error**.

---

# ⚠️ Common Causes of Errors

Errors can occur for many reasons throughout the software development life cycle.

### 1. Time Pressure

Tight deadlines can force team members to work quickly, increasing the likelihood of mistakes.

### 2. Human Fallibility

People naturally make mistakes. Even experienced developers, testers, analysts, and managers can misunderstand information or overlook details.

### 3. Lack of Experience or Skills

Inexperienced or insufficiently skilled project participants may make mistakes because they lack the required technical or domain knowledge.

### 4. Miscommunication

Poor communication between developers, testers, business analysts, customers, and other stakeholders can lead to misunderstandings.

### 5. Complexity

Complex code, architecture, business logic, integrations, or technologies can make it difficult to understand how the system should behave.

### 6. Interface Misunderstandings

Misunderstandings about **intra-system** or **inter-system interfaces** can introduce defects, especially when multiple components or external systems interact.

### 7. New or Unfamiliar Technologies

Working with technologies, frameworks, tools, or platforms that the team is unfamiliar with can increase the possibility of errors.

---

# 🔄 Bug Life Cycle

The **Bug Life Cycle**, also known as the **Defect Life Cycle**, describes the different states a defect can go through from the moment it is identified until it is resolved and closed.

A typical flow looks like this:
</br>
</br>

<p align="left"> <img src="https://raw.githubusercontent.com/abzaman7/BUGS_DEFECTS_and_FALIURES/main/imageye___-_imgi_15_bug-life-cycle-stages.png" alt="Bug Life Cycle Stages" width="800"> </p>

<!--```text
          ┌─────────────┐
          │     New     │
          └──────┬──────┘
                 ↓
          ┌─────────────┐
          │   Assigned  │
          └──────┬──────┘
                 ↓
          ┌─────────────┐
          │    Open     │
          └──────┬──────┘
                 ↓
          ┌─────────────┐
          │ In Progress │
          └──────┬──────┘
                 ↓
          ┌─────────────┐
          │    Fixed    │
          └──────┬──────┘
                 ↓
          ┌─────────────┐
          │    Retest   │
          └──────┬──────┘
                 ↓
          ┌─────────────┐
          │   Verified  │
          └──────┬──────┘
                 ↓
          ┌─────────────┐
          │    Closed   │
          └─────────────┘
```-->
</br>

Depending on the organization's workflow, a defect may also move into states such as:

* **Rejected**
* **Duplicate**
* **Deferred**
* **Won't Fix**
* **Cannot Reproduce**
* **Reopened**

The exact workflow may vary depending on the project's processes and defect management tool.

---

## 📌 Key Takeaways

| Term               | Meaning                                                                     |
| ------------------ | --------------------------------------------------------------------------- |
| **Error**          | A human mistake                                                             |
| **Defect**         | A flaw introduced into a work product                                       |
| **Failure**        | Incorrect behavior observed when a defect is executed                       |
| **Bug**            | Commonly used term for a defect in software                                 |
| **Bug Life Cycle** | The series of states a defect passes through from identification to closure |

### Remember

```text
Error → Defect → Failure
```

A **human error** can introduce a **defect**, and when that defect is executed under the right conditions, it can result in a **failure**.

Understanding this relationship helps QA professionals not only identify defects but also understand **how and why they were introduced**, which is essential for preventing similar issues in the future.
