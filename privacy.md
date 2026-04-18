---
layout: default
title: Privacy Policy
permalink: /privacy/
---

# Privacy Policy — PDF Word Extractor

**Last updated:** 18 April 2026

PDF Word Extractor (“the app”) is designed to keep your activity on your device. This page describes exactly what the app does with data so you can decide whether to use it.

## Summary

- The app does **not** have user accounts, analytics, advertising, or third-party trackers.
- The app does **not** collect personal information.
- The only data that leaves your device is a single word at a time, sent to Wiktionary when you tap a word to see its definition.
- Words you have looked up, the definitions returned, and the filenames of PDFs you have scanned are stored **only on your device**.

## What data the app handles

### Words you tap

When you tap a word in the app, the app sends that word in an HTTPS request to the Wiktionary edition that matches the word's detected language — English words go to `en.wiktionary.org`, Spanish to `es.wiktionary.org`, French to `fr.wiktionary.org`, and so on across the twelve supported languages. The request contains only:

- The word itself (URL-encoded in the request path).
- A standard `User-Agent` header identifying the app (`pdf-dict/1.0`).

The app does **not** attach any account identifier, device identifier, advertising identifier, IP-based identifier, location, or other personal data to this request. Wiktionary (operated by the Wikimedia Foundation) may log standard HTTP request metadata such as the source IP address, as described in the [Wikimedia Privacy Policy](https://foundation.wikimedia.org/wiki/Privacy_policy).

### PDFs you open

PDFs that you pick with the in-app document picker, receive through the iOS share sheet, or open via the `wordmint://` URL scheme are processed **entirely on your device**. The PDF contents are never uploaded anywhere. PDFs shared into the app via the Share Extension are copied into the app’s own App Group container, processed, and then deleted; stale copies older than seven days are cleaned up automatically on launch.

### Words and definitions you have seen

When you look up a word successfully, the app saves the normalised word, the returned definition text, and the detected language to a local SwiftData database. When you finish processing a PDF, the app also saves the PDF's filename, the list of unique words it contained, the detected language, and the scan date as a separate record so you can revisit it from the Library tab. Both stores live only on your device (or, if you have iCloud Drive or iCloud Backup enabled, inside your own personal iCloud backup, under your control). Neither is ever transmitted to the developer or to any third party. Deleting a PDF from the Library also removes any seen-words that were unique to that PDF; shared words stay because another saved PDF still references them.

### Camera (optional feature)

The Camera tab uses the device camera, via Apple’s on-device Vision framework, to detect words in printed text. The camera feed and all OCR processing remain on the device. Camera frames and OCR results are never uploaded anywhere.

## What the app does **not** do

- No accounts, logins, or user identifiers.
- No analytics SDKs, crash reporting SDKs, or advertising SDKs.
- No location data is requested or used.
- No contact, calendar, photo library, or microphone access is requested.
- No cross-site tracking, no data brokers, no data selling.

## Children

The app is suitable for general audiences. Because the app collects no personal data, there is no special handling required for children’s data under COPPA or similar frameworks.

## Data retention and deletion

All app data lives locally on your device. To delete everything:

1. Open the iOS **Settings** app.
2. Go to **General → iPhone Storage** (or **iPad Storage**).
3. Select **PDF Word Extractor**.
4. Tap **Delete App**.

Deleting the app removes the local SwiftData database and any PDFs stored in the app’s App Group container.

## Required-Reason API declarations

iOS apps that use certain APIs must declare a reason in a privacy manifest. The app declares:

- `NSPrivacyAccessedAPICategoryFileTimestamp` — reason `C617.1`, to check modification times of PDFs stored in the app’s own App Group container (used to clean up stale shared files).
- `NSPrivacyAccessedAPICategoryUserDefaults` — reason `1C8F.1`, to share a single path string between the main app and the Share Extension via an App Group.

These declarations match the behaviour described above; no other required-reason APIs are used.

## Changes to this policy

If this policy changes, the updated version will be published at this URL with a new **Last updated** date.

## Contact

Questions about this policy can be sent to **alexfpalmero@gmail.com**.
