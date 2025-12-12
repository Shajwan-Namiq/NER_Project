Annotation Guidelines for Sorani Kurdish Named Entity Recognition (NER)
1. Introduction

This document describes the annotation guidelines used to create a Named Entity Recognition (NER) dataset for Sorani Kurdish.
The purpose of this dataset is to support the development and evaluation of machine learning models for automatically identifying named entities in Kurdish text.

The annotation process follows standard NLP practices and uses the BIO tagging scheme.

2. Annotation Objective

The main objective of this annotation task is to identify and label named entities in Sorani Kurdish text belonging to the following four categories:

PER – Person

ORG – Organization

LOC – Location

DATE – Date

Only these four entity types are used throughout the dataset.

3. Entity Definitions
3.1 Person (PER)

The PER label is used for names of real people, including politicians, doctors, public figures, and other individuals.

Examples:

مەسرور بارزانی

لیوا تەحسین خەفاجی

رێواز فایەق

Titles alone (e.g., “پزیشک”, “سەرۆک”) are not tagged unless they are part of a full name.

3.2 Organization (ORG)

The ORG label is used for names of organizations, institutions, ministries, governments, universities, media outlets, and official bodies.

Examples:

وەزارەتی بەرگریی عێراق

حکومەتی هەرێمی کوردستان

زانکۆی هارڤەرد

رووداو

3.3 Location (LOC)

The LOC label is used for geographical locations, including countries, regions, cities, provinces, and administrative areas.

Examples:

عێراق

هەرێمی کوردستان

سووریا

هەولێر

3.4 Date (DATE)

The DATE label is used for expressions referring to time, including days, months, years, and complete calendar dates.

Examples:

2025

چوارشەممە

19ی تشرینی دووەمی 2025

4. BIO Tagging Scheme

All entities are annotated using the BIO format:

B-XXX: Beginning of an entity

I-XXX: Inside an entity

O: Outside any named entity

Example:
مەسرور   B-PER
بارزانی  I-PER
لە       O
هەولێر   B-LOC


Each entity must start with a B- tag, followed by I- tags if the entity consists of multiple tokens.

5. Data Format

Each token is placed on a separate line

Each line follows the format:

TOKEN<TAB>TAG


Sentences are separated by a blank line

Article identifiers (e.g., article1, article2) are not part of the annotation

6. Annotation Rules

Only the four entity types (PER, ORG, LOC, DATE) are allowed.

Tokens that are not part of any named entity must be labeled as O.

Multi-word entities must use B- for the first word and I- for subsequent words.

Punctuation marks are always labeled as O.

Ambiguous cases are resolved using context.

No nested or overlapping entities are allowed.

7. Excluded Entity Types

The following entity types are explicitly excluded from this dataset:

EVENT

FAC (Facility)

PRODUCT

TIME

MONEY

Any occurrences of these concepts are labeled as O.

8. Quality Control

All annotations were manually reviewed.

Invalid or inconsistent tags were removed.

The final dataset contains only valid BIO labels.

The annotation was checked for format consistency before model training.

9. Dataset Usage

This dataset is used to:

Train a CRF-based NER model for Sorani Kurdish

Evaluate model performance using precision, recall, and F1-score

Provide a baseline for future work using deep learning and transformer-based models

10. Final Notes

These guidelines ensure consistency, reproducibility, and clarity in the annotation process.
They also allow future researchers to extend the dataset or compare results using the same annotation standards.