# Task 1: Email to Ticket Automation

## Overview

This task involved building an automated workflow that eliminates the manual process of creating support tickets from incoming emails. Before this solution, a member of the IT team had to read every email sent to the support mailbox, assess its urgency, and manually create a task in Microsoft Planner. This was slow, inconsistent, and created delays in responding to users.

The solution is a Microsoft Power Automate cloud flow that monitors the shared support mailbox and handles the entire process automatically from the moment an email arrives.

## Problem Statement

The support team was receiving emails at the shared support mailbox and manually creating Planner tasks for each one. This manual process caused inconsistent prioritisation, missed tickets during busy periods, and no standardised way to track who was responsible for each issue.

## Solution

A Power Automate cloud flow was built and configured to run the following steps automatically every time a new email arrives in the support mailbox.

The flow detects the incoming email and extracts the subject, body, sender name, and sender email address. It then scans the subject and body for priority keywords to determine whether the issue is P1 Critical, P2 High, P3 Medium, or P4 Low. Based on this classification it creates a task in the correct Microsoft Planner bucket with the appropriate labels and due date. Finally it sends an automated confirmation reply to the sender acknowledging receipt of their request.

## Priority Classification

| Priority | Keywords Detected | Planner Bucket | Response Target |
|----------|-------------------|----------------|-----------------|
| P1 Critical | urgent, down, outage, critical, broken | P1 Critical | 1 hour |
| P2 High | not working, error, failing, asap, blocked | P2 High | Same business day |
| P3 Medium | issue, problem, slow, intermittent, help | P3 Medium | 48 hours |
| P4 Low | All other emails | Unassigned Queue | 5 business days |

## Label Taxonomy

Every task created in Planner receives four labels automatically applied from the email content.

Team Assignment identifies which team owns the ticket based on keywords in the email body. Priority captures the P1 to P4 classification. Type categorises the issue as a Bug, Feature Request, Access issue, Billing query, or General enquiry. Reporter is automatically populated from the sender email address so every ticket has a clear audit trail.

## Tools Used

Microsoft Power Automate, Microsoft Planner, Exchange Online shared mailbox, Microsoft 365

## What I Learned

Building this flow taught me how to use Power Automate connectors for Outlook and Planner, how to implement conditional logic using keyword matching across multiple branches, how to use dynamic content from email triggers to populate task fields, and how to structure an automation that handles edge cases such as empty email bodies and unclassifiable content.
