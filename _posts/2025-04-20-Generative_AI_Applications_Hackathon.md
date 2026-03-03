---
layout: post
title: "Generative AI Applications Hackathon | AWS & Agentic LLM"
date: "2025-04-20 09:00:00"
categories: Extracurricular_Activities
tags: Competition
comments: 1
published: true
---

> Developing an Agent-based Patient Care System using AWS and Generative AI.

![Post]({{site.baseurl}}/assets/res/post.png){:height="50%" width="50%"}

In the Generative AI Applications Hackathon, our team built a prototype for an automated patient care system. The system uses vision-based AI to monitor patient status and provides intelligent responses via a large language model.

Technical Workflow:

1. **Data Capture**: Controlled an Advantech industrial camera via Linux (Ubuntu) to capture patient facial expressions and movements.
2. **Streaming**: Streamed video data to AWS S3 using AWS Kinesis for real-time processing.
3. **Inference & Orchestration**: Utilized AWS Bedrock for LLM inference and AWS Lambda to handle the logic for generating proper care replies based on the captured emotional data.
4. **Agent Workflow**: Constructed an end-to-end agentic workflow that translates sensor input into empathetic and accurate clinical responses.

This project demonstrated the potential of integrating hardware, cloud infrastructure, and Agentic LLMs to enhance the efficiency of healthcare services.
