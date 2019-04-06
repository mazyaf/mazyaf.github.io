# Android Custom View Tutorial (Part 1\. – Combining Existing Views

## Introduction

The Android framework has a large variety of View classes that cover many of the needs of a typical Android application. These views, along with the multitude of options for using drawable resources, make it possible to create complex user interfaces for Android applications. Nevertheless, as with just about any framework, sometimes existing classes do not fit your needs and you need to create your own.

When we set out to create a mobile solution for our time entry system, we decided that we wanted to create something that was not merely convenient and functional, but also pleasant and enjoyable to use. More so than any other platform that I have developed for, mobile applications are judged based on UI and UX (User Interface and User Experience). Have you ever deleted a mobile app simply because it was too confusing or just plain ugly? You would not be alone if you answered yes.

Learning how to create Android custom views is a valuable skill for creating great Android applications. With this tool under your belt, you have nearly unlimited flexibility in the UI/UX design of your app, helping you create apps that users will enjoy. As you will see in this tutorial, there is definitely a learning curve, but I think you will find it worth the effort.

## Custom Views in Android

There are generally two approaches to creating your own view: extend an existing view or create one from scratch (well, not totally from scratch since you will still be extending the View class). This article focuses on extending an existing view. More specifically, we will be extending an existing layout and combining existing views to form a new Android custom view.
This post is part of an Android Custom View Tutorial series for Creating Custom Views in Android. All of the code for this tutorial is available in the (example application) [https://github.com/IntertechInc/android-custom-view-tutorial] , which demonstrates the custom views.

This Android Custom View Tutorial series assumes you are familiar with working with views in Android. It does not cover topics such defining views in xml, referencing values in resource files, etc.

##Combining Existing Views

Why would you want you combine existing views? What is the advantage over simply placing those views individually in the layout? There are a couple of reasons. First, if you have several views that are needed to represent a single model object, it is convenient to have a custom view that handles populating those individual child views. That way you can simply pass the model object to the custom view, instead of having to populate each of those views individually every time. Second, if you have a collection of views that need to work together (e.g. actions performed on one view affect others), a custom view makes a nice container for the logic that ties them together. Additionally, if these UI portions are reused throughout your application, then an Android custom view is even more practical.

To illustrate, we are going to create the following view:

![alt text] (https://www.intertech.com/Blog/wp-content/uploads/2015/07/value_selector.png)
