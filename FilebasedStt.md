---
tags: [API Reference Document]
---


> Use the STT API to convert the speech into Indic language scripts. This document describes the available variables, commands, and interfaces that make up the Reverie STT API. The API is platform-agnostic, organized around REST. All requests are made over HTTPS. All response bodies, including errors, are delivered in JSON. <br/> This document will help developers implement Speech-to-Text (STT)/ Automated Voice Recognition (ASR) in their applications.

# Text-to-Speech API (TTS API)
Reverie's TTS (Text-to-Speech) is a solution that turns text into lifelike speech, allowing you to create applications that talk in multiple Indic languages and build comprehensive speech-enabled products.
The Reverie TTS service will offer neural Text-to-Speech voices, delivering innovative enhancements in speech quality through state-of-the-art machine learning approaches. You can select the ideal voice and tone to build the natural and human-like speech-enabled applications in the market to enable the interactive customer experience.
## Supporting Languages
The TTS solution will understand popularly used ten languages using customizable voice and offer services to all the domains like Telecom, Banking, Entertainment, etc.:

|1. Hindi   |2. Marathi |3. Odia    |4. Bengali|
|-----------|-----------|-----------|-----------|
|**5. Tamil   **|**6. Kannada **|**7. Telugu  **|**8. Malayalam**|
|**9. Gujarati**|**10. Indian English**|||

>_**Note**: Our Research and Development team is continuously working to enable all the leading Indian languages on the Text-to-Speech platform with new voices across all the languages and strive to enhance the existing model’s accuracy._

## Key Feature
Reverie TTS API delivers remarkable robust features that effectively serve consumers in their native Indian language:
* **Faster than Real-time Speech Synthesis**
    
    The TTS API will swiftly synthesize the speech output, consuming less time than the time consumed to speak in real-time.  This enables real-time user experience for your users using the application.

* **Customize the Speech Model**

    Train the text-to-speech solution to suit your requirements. The Reverie TTS will support lexicons and SSML tags, which allow you to manage the speech aspects like volume, pitch, speed rate, the pronunciation of words with context, etc.

* **Text and SSML Support**

    Customize your speech with SSML tags that allow you to add pauses, numbers, date and time formatting, and other pronunciation instructions.

* **High-Quality & Accurate Pronunciation**    

    Attune your speech with SSML tags that allow you to add pauses, numbers, date and time formatting, and other pronunciation instructions, enabling you to deliver an accurate and high-quality voice-output.

* **Optimize Your Speech Output**    

    You can choose from various sampling rates to optimize bandwidth and audio quality for your application. The Reverie TTS supports WAV, OGG, MP3, FLAC, Ogg Opus, and PCM audio formats with sampling rates ranging from 8kHz, 16kHz, 22.05kHz, 24kHz, 44.1kHz, and 48kHz.

* **Branded Custom Voices**    

    We work with you on your voice requirements, select voice characteristics, and create and test your voice until it's ready to stand out of the crowd.

## Benefits of Reverie TTS
Reverie’s TTS should be your selection to build a comprehensive speech application because:
* Extensive depository of lifelike voices
* AI-optimized text processing
* Dedicated support for multiple Indic languages
* Allows customization to create unique voice personas

# Getting Started

The TTS API establishes the connection using the HTTPS protocol. It uses standard HTTP codes, authentication, and verbs. It will allow you to synthesize high-quality spoken audio in multiple formats. You’ll always receive audio data or an error message in the same HTTP transaction.

The `REV-APPNAME` parameter in the Header will identify the requested API. The API will recognize the default settings like languages, SSML tag settings by the `REV-APP-ID`, and `REV-API-KEY` for each customer account.
> **Note:** _On receiving your request, the_ `REV-APP-ID` _and the_ `REV-API-KEY` are forwarded to your email ID to test the API.
# Getting Started

The TTS API establishes the connection using the HTTPS protocol. It uses standard HTTP codes, authentication, and verbs. It will allow you to synthesize high-quality spoken audio in multiple formats. You’ll always receive audio data or an error message in the same HTTP transaction.

The `REV-APPNAME` parameter in the Header will identify the requested API. The API will recognize the default settings like languages, SSML tag settings by the `REV-APP-ID`, and `REV-API-KEY` for each customer account.

> **Note:** _On receiving your request, the_ `REV-APP-ID` _and the_ `REV-API-KEY` _are forwarded to your email ID to test the API._

## Authentication

The TTS API will use the App Id and API key to authenticate requests. Your credentials carry many privileges, so be sure to keep them secure.
Use your App Id and API Key by assigning it to `REV-APP-ID` and `REV-API-KEY`, respectively.

## How does API work?

The process to generate an audio file for the text input is:

1.  Post the request by:

     a. Enter the valid `REV-APPNAME`, `REV-APP-ID`, and `REV-API-KEY`

    b. Define the `Speaker Code`

    c. Enter the text or for which you want to obtain the speech

    d. Define the SSML Code, if required

2.  By default, the API will return the WAV audio file with a sampling rate of 22.05KHz.

## Sample Code

-   **Request: Synthesizing Audio for Single Sentence**

```json http
{
  "method": "post",
  "url": "https://revapi.reverieinc.com/",
  "headers": {
    "REV-API-KEY": "eccfabc31c0a4ced213e40301663d5bd068cc9fe",
    "REV-APP-ID": "com.test",
    "REV-APPNAME": "tts",
    "speaker": "hi_female",
    "Content-Type": "application/json"
  },
  "body": {
    "text": "बंगलौर से हुबली तक ट्रेन की जाँच करें",
    "speed": 0.9,
    "pitch": 1
  }
}
```

-   **Request: Synthesizing Audio for Multiple Sentence**

```json http
{
  "method": "post",
  "url": "https://revapi.reverieinc.com/",
  "headers": {
    "REV-API-KEY": "eccfabc31c0a4ced213e40301663d5bd068cc9fe",
    "REV-APP-ID": "com.test",
    "REV-APPNAME": "tts",
    "speaker": "hi_female",
    "Content-Type": "application/json"
  },
  "body": {
  "text":  ["भारत मेरा देश है।" , "मेरी कंपनी का नाम रेवेरी लैंग्वेज टेक्नोलॉजीज है।" ], 
	"speed": 1,
	"pitch": 0.9,
	"format": "MP3"
  }
}
```
-   **Request: Passing SSML Tag & Synthesizing Audio**

```json http
{
  "method": "post",
  "url": "https://revapi.reverieinc.com/",
  "headers": {
    "REV-API-KEY": "eccfabc31c0a4ced213e40301663d5bd068cc9fe",
    "REV-APP-ID": "com.test",
    "REV-APPNAME": "tts",
    "speaker": "hi_female",
    "Content-Type": "application/json"
  },
  "body": {
  "text": "<say-as interpret-as='\''currency'\''>€10.50</say-as>", 
	"speed": 1,
	"pitch": 0,
	"format": "FLAC"
  }
}
```

