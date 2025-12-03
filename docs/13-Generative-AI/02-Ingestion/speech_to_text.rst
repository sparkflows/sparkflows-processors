Audio Diarization
===========

This node processes audio files to transcribe and diarize speech, identifying different speakers in the audio. It generates a structured output as a DataFrame with two columns: speaker and dialogue.


Input
--------------
It takes directory or path as an input

Output
--------------
Outputs a Dataframe with 2 columns speaker and dialouge

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeSpeechToText

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - audioFilePath
        - Directory Or File Path
        - Select a Pdf/Text/Docx File or Directory
      * - numSpeakers
        - Number of Speakers
        - Provide the number of speakers expected in the conversation.
      * - diarization
        - Diarization
        - Diarise the transcription.
      * - saveOutputPath
        - Output Save Path
        - Specify the file path to save the transcription output as a .txt file.
      * - context
        - Additional Context
        - Add any relevant context or details about the conversation to help improve the diarization.
      * - openai
        - OpenAI
        - 
      * - llmConnection
        - Select Connection
        - Select Connection
      * - openaiModel
        - OpenAI Model
        - OpenAI Model to be Used


Details
-------
Audio Diarization Node Details
+++++++++++++++

The Audio Diarization node processes audio files to transcribe speech and, optionally, diarize it by identifying different speakers. It uses OpenAI's Whisper model (or other specified models) to generate a structured DataFrame output with two columns: speaker and dialogue. This node is ideal for extracting and organizing spoken content from audio files in PySpark-based data pipelines.



General:
+++++++++++++++



Directory Or File Path: Specifies the path to a single audio file or a directory containing multiple audio files. This field is required and must be accessible to the PySpark engine.
+++++++++++++++



Number of Speakers: Specifies the expected number of speakers in the audio. Default is 1. If set to 1, diarization is not applied, and all dialogue is attributed to a single speaker. Must be an integer.
+++++++++++++++



Diarization: Controls whether speaker diarization is performed. Options are:
+++++++++++++++


* true: Enables diarization to identify and label different speakers in the audio.
* false: Disables diarization, treating all dialogue as coming from a single speaker (default).


Output Save Path: Specifies the file path to save the transcription output as a .txt file. This is optional; if provided, the transcribed text is saved to the specified location.
+++++++++++++++



Additional Context: Allows users to provide additional context or details about the conversation (e.g., speaker names, accents, or topics) to improve transcription and diarization accuracy. This is optional.
+++++++++++++++



OpenAI Configuration:
+++++++++++++++



Select Connection: Specifies the connection details for the OpenAI API (e.g., API key). This is required to authenticate and access the OpenAI model.
+++++++++++++++



OpenAI Model: Specifies the OpenAI model to use for transcription. Default is 'whisper-1'. Other compatible models can be specified if supported by the OpenAI API.
+++++++++++++++



Output:
+++++++++++++++


The node outputs a DataFrame with the following columns:


* speaker: The identified speaker label (e.g., Speaker_1, Speaker_2, or 'Default' if diarization is disabled).
* dialogue: The transcribed text corresponding to the speaker's speech.

If the Output Save Path is specified, the transcription is also saved as a .txt file at the provided location.


Examples
-------
Example: Audio Diarization Node
+++++++++++++++



Input:
+++++++++++++++

A directory /data/audio/ contains the following file:


* meeting_recording.wav (a 5-minute audio file with two speakers discussing a project)


The Audio Diarization node is configured as follows:


* Directory Or File Path: /data/audio/meeting_recording.wav
* Number of Speakers: 2
* Diarization: true
* Output Save Path: /data/output/transcription.txt
* Additional Context: "Conversation between a project manager and a developer discussing project milestones."
* Select Connection: Configured with a valid OpenAI API key
* OpenAI Model: whisper-1


Output:
+++++++++++++++


The node processes the audio file and produces a DataFrame with the following structure:


::

    speaker     | dialogue
    ------------|--------------------------------------
    Speaker_1   | Let's discuss the project timeline...
    Speaker_2   | Sure, we need to finalize the milestones...
    Speaker_1   | I think we should prioritize the testing phase...
    Speaker_2   | Agreed, but we need more resources for that...


The transcription is also saved as /data/output/transcription.txt with the content:


* Speaker_1: Let's discuss the project timeline...
* Speaker_2: Sure, we need to finalize the milestones...
* Speaker_1: I think we should prioritize the testing phase...
* Speaker_2: Agreed, but we need more resources for that...



Explanation:
+++++++++++++++

* The meeting_recording.wav file is processed using the OpenAI Whisper-1 model.
* With Diarization set to true and Number of Speakers set to 2, the node identifies two distinct speakers and labels them as Speaker_1 and Speaker_2.
* The dialogue column contains the transcribed text for each speaker's segment.
* The Additional Context ("Conversation between a project manager and a developer...") helps improve the accuracy of transcription and diarization by providing relevant information about the conversation.
* The transcription is saved as a .txt file in /data/output/transcription.txt as specified in the Output Save Path.
* If Diarization was set to false or Number of Speakers was set to 1, all dialogue would be attributed to a single speaker labeled 'Default'.
