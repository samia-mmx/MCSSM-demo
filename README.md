<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8"/>
    <meta name="viewport" content="width=device-width,initial-scale=1"/>
    <title>Audio Samples</title>
    <style>
        body {
            margin: 0;
            padding: 10px 30px;
            background: #fff;
            color: #111;
            font-size: 15px;
            font-family: sans-serif;
            font-weight: 400;
            line-height: 1.8;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }

        audio {
            width: 290px !important;
            margin-right: 1px;
        }

        .sample {
            font-size: 0.9em;
            font-style: italic;
            border: 1px solid #ddd;
            padding: 1em;
            margin-bottom: 1em;
        }
    </style>
</head>
<body>
<h2>Learning Language and Speaker Information for End-to-End Code-Switch Speech Synthesis </h2>

<div><b>Authors:</b> Shaotong Guo , Mengxin Chai , Cheng Gong , Longbiao Wang , Jianwu Dang , Ju Zhang</div>
<!--     <div><b>Abstract:</b> State-of-the-art text-to-speech (TTS) synthesis models can produce monolingual speech with high intelligibility and naturalness. However, when the models are applied to synthesize code-switched (CS) speech, the performance declines seriously. Conventionally, developing a CS TTS system requires multilingual data to incorporate language-specific and cross-lingual knowledge. Recently, end-to-end (E2E) architecture has achieved satisfactory results in monolingual TTS. The architecture enables the training from one end of alphabetic text input to the other end of acoustic feature output. In this paper, we explore the use of E2E framework for CS TTS, using a combination of Mandarin and English monolingual speech corpus uttered by two female speakers. To handle alphabetic input from different languages, we explore two kinds of encoders: (1) shared multilingual encoder with explicit language embedding (LDE); (2) separated monolingual encoder (SPE) for each language. The two systems use identical decoder architecture, where a discriminative code is incorporated to enable the model to generate speech in one speaker's voice consistently. Experiments confirm the effectiveness of the proposed modifications on the E2E TTS framework in terms of quality and speaker similarity of the generated speech. Moreover, our proposed systems can generate controllable foreign-accented speech at character-level using only mixture of monolingual training data. </div> -->
<div><b>Abstract:</b> In this paper, we propose the use of language and speaker information and only use a small
    mix-lingual data to realize a CS synthesis of Mandarin and English. In order to distinguish the different languages
    in the input text, we explore two kinds of representation of text: (1) using different kinds of characters to
    represent the two languages (implicit); (2) using masks to separate
    different languages (explicit). What’s more, Our model having a speaker extraction module. The learned speaker
    information and traditional character features are fed into the decoder simultaneously for generating the final Mel
    spectrogram. We conduct
    a series of experiments on speaker consistency and the naturalness of speech.
</div>
<div><b>Notes:</b> In order to obtain best quality, we strongly encourage the listeners to take their headphones.</div>

<h3>Definition (same as defined in our submitted paper)</h3>
<div>
    <table>
        <!-- <tr><td> <strong>• single speaker CS (SCS): </strong>just have a text encoder.</td></tr> -->
        <tr>
            <td><strong>• muti-speaker CS with speaker embedding and mask embedding (MCSSM): </strong>
                with language marker encoder, text encoder and speaker feature encoder.
            </td>
        </tr>
        <tr>
            <td><strong>• muti-speaker CS with speaker embedding (MCSS): </strong>
                with text encoder and speaker feature encoder.
            </td>
        </tr>
        <tr>
            <td><strong>• muti-speaker CS with mask embedding (MCSM): </strong>
                with language marker encoder, text encoder and speaker feature encoder.
            </td>
        </tr>
    </table>
</div>

<div>
    <h3><strong>Speaker Consistency:</strong> Evaluate whether it is the same speaker</h3>
</div>

<table style="width:50%">

    <tr>
        <th style="width:10%"></th>
        <th style="width:40%">Ground Truth</th>
        <th style="width:40%">MCSSM</th>
    </tr>
</table>

<table >
    <tr>
        <th align="left">Speaker 1</th>
        <th >
             <audio controls="" style="width: 100px;">
                <source src="./hxt_000170.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
        </th>
        <th >
             <audio controls="" style="width: 100px;">
                <source src="./mcsse_hxt_spe1_0.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
        </th>
    </tr>
</table>

<table >
    <tr>
        <th align="left">Speaker 2</th>
        <th>
             <audio controls="" style="width: 100px;">
                <source src="./004_zjk_006435.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
        </th>
        <th>
             <audio controls="" style="width: 100px;">
                <source src="./mcsse_zjk_spe2_0.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
        </th>
    </tr>
</table>

<table>
    <tr>
        <th align="left">Speaker 3</th>
        <th>
             <audio controls="" style="width: 100px;">
                <source src="./006_000002.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
        </th>
        <th>
             <audio controls="" style="width: 100px;">
                <source src="./mcsse_006_spe3_0.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
        </th>
    </tr>
</table>


<h3>Results </h3>

<p><i>Text："它正在收购的耳机企业BEAT。"</i></p>
<table>
    <tr>
          <th style="width:10%" align="left">Speaker 1</th>
          <th style="width:40%"> </th>
          <th style="width:40%"></th>
    </tr>
</table>
<table style="width:27.5%">
    <tr>
          <th  align="left" ><small>MCSSM</small></th>
          <th  align="right">
             <audio controls="" style="width: 100px;">
                <source src="./mcsse_hxt_speaker1_18beat.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
          </th>
    </tr>
</table>
<table style="width:27.5%">
    <tr>
          <th style="width:10%" align="left"><small>MCSS</small></th>
          <th style="width:40%" align="right">
             <audio controls="" style="width: 100px;">
                <source src="./mcss_hxt_speaker1_18.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
          </th>
    </tr>
</table>


<table>
    <tr>
          <th style="width:10%" align="left">Speaker 2</th>
          <th style="width:40%"> </th>
          <th style="width:40%"></th>
    </tr>
</table>
<table style="width:27.5%">
    <tr>
          <th  align="left" ><small>MCSSM</small></th>
          <th  align="right">
             <audio controls="" style="width: 100px;">
                <source src="./mcsse_zjk_speaker2_18.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
          </th>
    </tr>
</table>
<table style="width:27.5%">
    <tr>
          <th style="width:10%" align="left"><small>MCSS</small></th>
          <th style="width:40%" align="right">
             <audio controls="" style="width: 100px;">
                <source src="./mcss_zjk_speaker2_15.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
          </th>
    </tr>
</table>

<table>
    <tr>
          <th style="width:10%" align="left">Speaker 3</th>
          <th style="width:40%"> </th>
          <th style="width:40%"></th>
    </tr>
</table>
<table style="width:27.5%">
    <tr>
          <th  align="left" ><small>MCSSM</small></th>
          <th  align="right">
             <audio controls="" style="width: 100px;">
                <source src="./mcsse_006_speaker1_18.wav.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
          </th>
    </tr>
</table>
<table style="width:27.5%">
    <tr>
          <th style="width:10%" align="left"><small>MCSS</small></th>
          <th style="width:40%" align="right">
             <audio controls="" style="width: 100px;">
                <source src="./mcss_006_speaker3_18.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
          </th>
    </tr>
       <tr>
          <th  align="left" ><small>MCSM</small></th>
          <th  align="right">
             <audio controls="" style="width: 100px;">
                <source src="./mcse_006_speaker3_18.wav" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
          </th>
    </tr>
</table>
</body>
</html>
