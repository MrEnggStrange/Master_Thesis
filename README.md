 
# 📡 ASCII Acknowledgment Response System for G4 Product Platforms

> **Author:** Joe Joseph Nelson  
> **University:** Hochschule Bremerhaven  
> **Company:** Wenglor MEL GmbH  
> **Degree:** M.Sc. in Embedded Systems Design  
> **Date:** December 6, 2024

## 📘 Abstract

This repository contains the core work and architecture behind a scalable **ASCII Acknowledgment Response System** implemented for **ShapeDrive G4 sensors**, high-precision 3D machine vision devices used in industrial automation. The primary objective of this thesis is to design and implement a robust, modular, and low-latency ASCII command acknowledgment system using **XML containers**, enhancing command feedback, reliability, and debugging capabilities of the embedded sensor firmware.

## 🧠 Motivation

G4 sensors lacked an active acknowledgment mechanism for executed commands, creating uncertainty in mission-critical applications like:

- 📦 Bin Picking (Automotive Industry)
- 🥩 Precise Meat Cutting (Food Industry)

This project solves that by providing structured, real-time XML-based feedback for every command execution.

## 🎯 Goals

- Design and develop an **acknowledgment handler** for ASCII commands.
- Implement acknowledgment responses using a **well-structured XML container** format.
- Improve **user feedback**, **command validation**, and **debugging** capabilities.
- Ensure **scalability**, **real-time performance**, and **backward compatibility**.

## 🧱 System Architecture

### 📦 Components

- **Processing System (PS)**: Executes configuration commands.
- **Programmable Logic (PL)**: Handles real-time 3D computation.
- **WeDevTool**: A TCP-based developer interface used for testing ASCII commands.
- **Ports**:
  - `32000`: ASCII Command Port
  - `32001`: Data/Response Port

### 🗂 Modified melApp Architecture

A centralized **command handler** and **acknowledgment generator** were integrated into the existing firmware. It parses, executes, and returns acknowledgments as XML via the data port.

## ⚙️ Features

- ✅ **Modular Command Handler**
- 🧪 **Unit, Integration, and Stress Testing**
- 📄 **XML-based Response Format**  
  Example:
  ```xml
  <acknowledgment>
    <command>SetGain</command>
    <user_value>25</user_value>
    <current>24</current>
    <min>0</min>
    <max>50</max>
    <execution_time>15ms</execution_time>
  </acknowledgment>

- 🔍 Command Validation

- 🧰 Error Handling with CRC

- 🏷 Command Classification:

- COMMAND_TYPE_ACTION

- COMMAND_TYPE_ENUM_PARAM

- COMMAND_TYPE_RANGE_PARAM

- COMMAND_TYPE_ACK_CHECK

- COMMAND_TYPE_NO_ACK
