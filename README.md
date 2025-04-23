<meta name="viewport" content="width=device-width, initial-scale=1.0">

<h1>AlignDiT: Multimodal Aligned Diffusion Transformer<br>for Synchronized Speech Generation</h1>

<h3><i>Anonymous submission to ACMMM 2025</i></h3>

<div style="width:100%; margin-top: 20px; margin-bottom: 20px;">
<img align="center" src="imgs/fig1.png" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;"  /></div>

<h2>Abstract</h2>
<div style="width:100%; max-width: 720px; margin-bottom: 20px; margin-left: auto; margin-right: auto;">
<p>In this paper, we address the task of multimodal-to-speech generation, which aims to synthesize high-quality speech from multiple input modalities: text, video, and reference audio. This task has gained increasing attention due to its wide range of applications, such as film production, dubbing, and virtual avatars. Despite recent progress, existing methods still suffer from limitations in speech intelligibility, audio-video synchronization, speech naturalness, and voice similarity to the reference speaker. To address these challenges, we propose AlignDiT, a multimodal Aligned Diffusion Transformer that generates accurate, synchronized, and natural-sounding speech from aligned multimodal inputs. Built upon the in-context learning capability of the DiT architecture, AlignDiT explores three effective strategies to align multimodal representations. Furthermore, we introduce a novel multimodal classifier-free guidance mechanism that allows the model to adaptively balance information from each modality during speech synthesis. Extensive experiments demonstrate that AlignDiT significantly outperforms existing methods across multiple benchmarks in terms of quality, synchronization, and speaker similarity. Moreover, AlignDiT exhibits strong generalization capability across various multimodal tasks, such as video-to-speech synthesis and visual forced alignment, consistently achieving state-of-the-art performance.</p>
</div>

<h2>Comparison results on LRS3 dataset</h2>
<table border="0" width="100%" style="border-spacing: 0; border-collapse: collapse;">
  <thead>
    <tr>
      <th align="center"><strong>Text<br>(Input)</strong></th>
      <th align="center"><strong>Silent Video<br>(Input)</strong></th>
      <th align="center"><strong>Reference Speech<br>(Input)</strong></th>
      <th align="center"><strong>Ground Truth</strong></th>
      <th align="center"><strong>AlignDiT (Ours)</strong></th>
      <th align="center"><strong>HPMDubbing</strong></th>
      <th align="center"><strong>StyleDubber</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><div style="width:192px; word-break:break-word;">this is possible</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/wlR1ojoiue0_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">that was powerful</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/jtVIDBs60S8_00001.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">my father worked at this factory he said</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/GMynksvCcUI_00001.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">they are doing it together</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/PSlBlZ3hqKc_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and he said well i just care so deeply about my customers that i would never sell them one of our crappy products</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/YyXRYgjQXX0_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">without it we literally can't interface with others</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/uzKBGtf0i0M_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and when i look at the criminal justice system in the united states today i feel the exact same way that i did about the state of</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/ZJNESMhIxQ0_00024.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and now i love languages</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/iPE2SiCCo0w_00021.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i'm also on this mission because the way doctors practice medicine continues to</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/KxLMjn4WPBY_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">they are gorgeous and headstrong brilliant girls who are a whole lot of brave</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/FxtSMZKMdes_00010.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">you're hearing one presentation after another often representing a group of people a tribe about how</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00039.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">a couple of years ago a group of us in canada decided that we were hitting the limits of what we could accomplish</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/JSSc7hYKstI_00015.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">well imagine you're walking in the forest and you see a bear</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/95ovIJ3dsNk_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i would listen to the heart</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/sxnlvwprfSc_00011.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">my dad has alzheimer's disease</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/J8FyHI00ELY_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">not the wife not the kids</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/nCg2NcGYu34_00006.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">all of you are members of tribes</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">if you want this experience to live on as something historic then at the reception</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00012.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">well very often we think about political change in defined compartments these days</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/JSSc7hYKstI_00010.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i know you understand that</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/SN7wO06Yz1E_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/hpmdubbing/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/styledubber/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
    </tr>
  </tbody>
</table>

<div style="width:100%; margin-top: 20px; margin-bottom: 20px;">
<img align="center" src="imgs/fig2.png" style="  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 100%;"  /></div>

<h2>Ablation study of modality conditioning method on LRS3 dataset</h2>
<table border="0" width="100%">
  <thead>
    <tr>
      <th align="center"><strong>Text<br>(Input)</strong></th>
      <th align="center"><strong>Silent Video<br>(Input)</strong></th>
      <th align="center"><strong>Reference Speech<br>(Input)</strong></th>
      <th align="center"><strong>Ground Truth</strong></th>
      <th align="center"><strong>(a)<br>w/o 𝓛_CTC</strong></th>
      <th align="center"><strong>(a)</strong></th>
      <th align="center"><strong>(b)<br>w/o 𝓛_CTC</strong></th>
      <th align="center"><strong>(b)</strong></th>
      <th align="center"><strong>(c)<br>w/o 𝓛_CTC</strong></th>
      <th align="center"><strong>(c)<br>AlignDiT</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><div style="width:192px; word-break:break-word;">this is possible</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/wlR1ojoiue0_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">that was powerful</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/jtVIDBs60S8_00001.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">my father worked at this factory he said</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/GMynksvCcUI_00001.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">they are doing it together</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/PSlBlZ3hqKc_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and he said well i just care so deeply about my customers that i would never sell them one of our crappy products</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/YyXRYgjQXX0_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">without it we literally can't interface with others</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/uzKBGtf0i0M_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and when i look at the criminal justice system in the united states today i feel the exact same way that i did about the state of</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/ZJNESMhIxQ0_00024.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and now i love languages</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/iPE2SiCCo0w_00021.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i'm also on this mission because the way doctors practice medicine continues to</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/KxLMjn4WPBY_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">they are gorgeous and headstrong brilliant girls who are a whole lot of brave</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/FxtSMZKMdes_00010.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">you're hearing one presentation after another often representing a group of people a tribe about how</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00039.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">a couple of years ago a group of us in canada decided that we were hitting the limits of what we could accomplish</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/JSSc7hYKstI_00015.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">well imagine you're walking in the forest and you see a bear</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/95ovIJ3dsNk_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i would listen to the heart</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/sxnlvwprfSc_00011.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">my dad has alzheimer's disease</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/J8FyHI00ELY_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">not the wife not the kids</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/nCg2NcGYu34_00006.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">all of you are members of tribes</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">if you want this experience to live on as something historic then at the reception</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00012.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">well very often we think about political change in defined compartments these days</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/JSSc7hYKstI_00010.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i know you understand that</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/SN7wO06Yz1E_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_a_ctc/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_b_ctc/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_c/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
    </tr>
  </tbody>
</table>

<h2>Ablation study of input modalities on LRS3 dataset</h2>
<table border="0" width="100%" style="border-spacing: 0; border-collapse: collapse;">
  <thead>
    <tr>
      <th align="center"><strong>Text<br>(Input)</strong></th>
      <th align="center"><strong>Silent Video<br>(Input)</strong></th>
      <th align="center"><strong>Reference Speech<br>(Input)</strong></th>
      <th align="center"><strong>Ground Truth</strong></th>
      <th align="center"><strong>Only Video</strong></th>
      <th align="center"><strong>Only Text</strong></th>
      <th align="center"><strong>AlignDiT (Ours)</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><div style="width:192px; word-break:break-word;">this is possible</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/wlR1ojoiue0_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/wlR1ojoiue0_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">that was powerful</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/jtVIDBs60S8_00001.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/jtVIDBs60S8_00001.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">my father worked at this factory he said</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/GMynksvCcUI_00001.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/GMynksvCcUI_00001.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">they are doing it together</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/PSlBlZ3hqKc_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/PSlBlZ3hqKc_00009.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and he said well i just care so deeply about my customers that i would never sell them one of our crappy products</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/YyXRYgjQXX0_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/YyXRYgjQXX0_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">without it we literally can't interface with others</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/uzKBGtf0i0M_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/uzKBGtf0i0M_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and when i look at the criminal justice system in the united states today i feel the exact same way that i did about the state of</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/ZJNESMhIxQ0_00024.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/ZJNESMhIxQ0_00024.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">and now i love languages</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/iPE2SiCCo0w_00021.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/iPE2SiCCo0w_00021.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i'm also on this mission because the way doctors practice medicine continues to</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/KxLMjn4WPBY_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/KxLMjn4WPBY_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">they are gorgeous and headstrong brilliant girls who are a whole lot of brave</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/FxtSMZKMdes_00010.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/FxtSMZKMdes_00010.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">you're hearing one presentation after another often representing a group of people a tribe about how</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00039.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00039.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">a couple of years ago a group of us in canada decided that we were hitting the limits of what we could accomplish</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/JSSc7hYKstI_00015.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/JSSc7hYKstI_00015.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">well imagine you're walking in the forest and you see a bear</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/95ovIJ3dsNk_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/95ovIJ3dsNk_00009.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i would listen to the heart</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/sxnlvwprfSc_00011.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/sxnlvwprfSc_00011.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">my dad has alzheimer's disease</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/J8FyHI00ELY_00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/J8FyHI00ELY_00002.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">not the wife not the kids</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/nCg2NcGYu34_00006.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/nCg2NcGYu34_00006.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">all of you are members of tribes</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00004.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">if you want this experience to live on as something historic then at the reception</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/xTkKSJSqUSI_00012.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/xTkKSJSqUSI_00012.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">well very often we think about political change in defined compartments these days</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/JSSc7hYKstI_00010.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/JSSc7hYKstI_00010.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td><div style="width:192px; word-break:break-word;">i know you understand that</div></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/silent/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><audio controls="controls" style="width: 128px;"><source src="audios/ref/SN7wO06Yz1E_00009.wav" autoplay/>Your browser does not support the audio element.</audio></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/gt/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_video/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/model_text/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
      <td style="text-align: center;"><video width="128" controls><source src="videos/aligndit/SN7wO06Yz1E_00009.mp4" type="video/mp4"></video></td>
    </tr>
  </tbody>
</table>
