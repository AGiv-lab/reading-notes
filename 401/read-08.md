# Reading 08 — Access Control (ACL)

## Role-Based Access Control

### What is RBAC, and why do we care?

**Role-Based Access Control (RBAC)** is a system for controlling access based on a person's assigned role within an organization or application.

Instead of assigning permissions separately to every user, permissions are assigned to roles. Users are then assigned the appropriate roles.

```text
User → Role → Permissions
```

RBAC matters because it:

- Prevents users from accessing features they do not need
- Reduces accidental or unauthorized changes
- Makes permissions easier to manage
- Supports the principle of least privilege
- Simplifies adding, removing, or changing users
- Makes security audits easier

> Authentication confirms who the user is. Authorization determines what that user is allowed to do.

---

## Example Role and Permission Hierarchy

An application might use the following roles:

| Role | Example Permissions |
| --- | --- |
| User | Read public content and update their own profile |
| Editor | User permissions plus create and edit content |
| Administrator | Editor permissions plus delete content and manage users |
| Super Administrator | Full system access, including roles and security settings |

A higher role may inherit the permissions of lower roles:

```text
Super Administrator
        ↓
Administrator
        ↓
Editor
        ↓
User
```

Every user should receive only the permissions required to complete their responsibilities.

---

## Five Steps for Implementing RBAC

### 1. Inventory the Systems

Identify the applications, databases, files, routes, and other resources that require controlled access.

### 2. Analyze Users and Create Roles

Group users according to common responsibilities and access needs. Avoid creating unnecessary roles.

### 3. Assign Users to Roles

Give each user the role or roles that match their responsibilities.

### 4. Avoid One-Off Permission Changes

Do not give random permissions directly to individual users. Update an existing role or create a justified new role instead.

### 5. Audit the System

Regularly review:

- Available roles
- Permissions assigned to each role
- Users assigned to each role
- Permissions that are no longer necessary

---

## Possible Implementation Approach

For an Express application, I might:

1. Define the available roles.
2. Define the capabilities allowed for each role.
3. Store a user's role in the user model.
4. Authenticate the user.
5. Use authorization middleware to check the user's role or capabilities.
6. Reject unauthorized requests with the appropriate status code.
7. Test every protected route.

Example role definitions:

```javascript
const roles = {
  user: ['read'],
  editor: ['read', 'create', 'update'],
  admin: ['read', 'create', 'update', 'delete'],
};
```

Example authorization flow:

```text
Request
   ↓
Authenticate User
   ↓
Identify Role
   ↓
Check Permission
   ↓
Allow or Deny Request
```

Access should be denied by default unless the user's role explicitly permits the requested action.

---

## Authentication and Authorization

### What is Authorization?

If authentication means:

> "You are who you say you are."

Authorization means:

> "You have permission to perform this action."

A user must normally authenticate before the application can determine which authorization rules apply.

| Process | Question Answered |
| --- | --- |
| Authentication | Who are you? |
| Authorization | What are you allowed to do? |

---

## Three Primary RBAC Rules

### 1. Role Assignment

A user can exercise a permission only if the user has been assigned an appropriate role.

### 2. Role Authorization

A user's active role must be an authorized role for that user. A user cannot simply choose a more powerful role.

### 3. Permission Authorization

A user can perform an action only if that action is permitted for the user's active role.

Together, these rules ensure that users can perform only the actions allowed by their assigned roles.

---

## RBAC Explained to a Non-Technical Friend

RBAC is similar to giving employees different keys at a workplace.

A customer may enter the public lobby. An employee badge may open staff areas. A manager's badge may open additional offices. Only an administrator may have access to the server room.

Access is based on the person's job role instead of creating a completely different set of keys for every individual.

---

## RBAC Tutorial Notes

### Are Access Rights Associated With the User or the Role?

Access rights are associated with the **role**.

The user is assigned a role, and the role provides the user's permissions.

```text
User B → Editor → Read, Create, Update
```

This makes access easier to maintain because changing the role updates permissions consistently for everyone assigned to it.

### When Is Authorization Activated?

Authorization occurs after the user successfully completes **authentication**, such as signing in with valid credentials or presenting a valid token.

The application first confirms the user's identity and then checks what that user is allowed to access.

### How Can RBAC Benefit a Business?

RBAC can help a business by:

- Protecting sensitive information
- Limiting employees to necessary resources
- Making onboarding and offboarding faster
- Reducing permission mistakes
- Making employee role changes easier
- Supporting regulatory and security requirements
- Providing more consistent access rules
- Simplifying audits

---

## ACL Compared With RBAC

An **Access Control List (ACL)** records which users or groups can perform specific actions on a resource.

For example:

```text
Document:
- Editors can read and update
- Customers can read
- Administrators can read, update, and delete
```

RBAC assigns permissions through roles, while an ACL commonly lists the permissions attached to a particular resource.

The two approaches can also be used together.

---

## Reflection

### What Are My Learning Goals?

After reviewing this material and the class README, my learning goals are to:

- Clearly explain authentication versus authorization
- Understand how users, roles, and permissions relate
- Add roles and capabilities to a user model
- Create middleware that checks permissions
- Protect Express routes using role-based authorization
- Apply least-privilege access
- Return appropriate errors for unauthorized requests
- Write tests for users with different roles
- Understand how JWTs and RBAC work together

---

## Things I Want to Know More About

- How role information is stored securely in a JWT
- The difference between roles and capabilities
- How to prevent a user from changing their own role
- When to use RBAC instead of an ACL
- How large applications manage hundreds of permissions
- How authorization middleware is tested

---

## Resources

- [Five Steps to Simple Role-Based Access Control](https://www.csoonline.com/article/555873/5-steps-to-simple-role-based-access-control.html)
- [Role-Based Access Control — Wikipedia](https://en.wikipedia.org/wiki/Role-based_access_control)
- [RBAC Tutorial](https://www.youtube.com/watch?v=C4NP8Eon3cA)
- [NIST Role-Based Access Control](https://csrc.nist.gov/projects/role-based-access-control/faqs)