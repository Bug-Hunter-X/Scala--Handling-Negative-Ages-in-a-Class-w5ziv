# Scala: Handling Negative Ages

This example showcases a subtle error related to data validation in a Scala class.  The `MyClass` attempts to prevent negative ages, but the error handling might not be immediately obvious to developers unfamiliar with Scala's property accessors.

## The Problem

The code uses a private backing field (`_age`) to manage the age, and a getter/setter for controlled access. However, the error handling is only in the setter; failure to consider negative values at the point of object creation or elsewhere could lead to unexpected behaviour.  The example throws an exception when a negative age is assigned directly.

## Solution

The solution below demonstrates several ways to improve the robustness of age handling. Using Option instead of exception is a good approach, handling edge cases appropriately.