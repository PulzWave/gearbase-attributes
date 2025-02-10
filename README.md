# GearBase Attributes

Welcome to the **GearBase Attributes** repository. This repository hosts the attribute data model for GearBase, providing a flexible and modular framework to define the characteristics of various gear items.

## Overview

In GearBase, a gear item is associated with a specific type. Each type can have one or more attributes, and the valid combinations are persisted in the `TypeAttribute` entity. The actual attribute values for a gear item are stored elsewhere (in `GearAttribute`), while this repository focuses on defining the data model for attributes and their relationships.

The data model consists of four key entities:

- **AttributeCategory**  
  Organizes attributes into logical groups (e.g., General, Features, Keybed, Sequencer, etc.) to streamline management and navigation.

- **Attribute**  
  Defines individual characteristics or properties that can be assigned to gear. Each attribute has a `dataType` which determines how its value is handled. There are four data types:
  - **boolean:** Represents a simple yes/no value
  - **date** Holds a date value
  - **integer:** Holds a numeric value
  - **string:** Provides a selectable value via a dropdown. The available options for a string attribute are predetermined in the `AttributeOption` entity (linked through the attribute-to-option relationship).
  - **multivalue:** Allows multiple selections from a set of predetermined options. The relationship between an attribute and its options is many-to-many.

- **AttributeOption**  
  Contains the predetermined choices for attributes that require a fixed set of values (used for string and multivalue attributes). This ensures consistency in data entry by limiting the available options.

NOTE: Due to the current codebase, AttributeOptions need to be unique. Hence you cannot use `No` as a value, instead it'll have to be `No screen` as an example.

- **TypeAttribute**  
  Represents the mapping between a gear type and its applicable attributes. It defines which attributes are available for a given type, thereby controlling which gear items can have which attributes.

## Contributing

We welcome contributions to improve and extend the attribute data model. If you have suggestions, enhancements, or bug fixes in mind, please start by creating an issue so we can discuss the proposed changes. While forking the repository and submitting a pull request is possible, it is not required—your feedback through issues is equally valuable.

## Core Functionality Issues

For any issues or discussions related to the core functionality of GearBase (outside of the attribute data model), please visit the dedicated repository:  
[GearBase Issues and Releases](https://github.com/PulzWave/gearbase-issues)

---

Thank you for your interest and contributions to the GearBase Attributes project!
