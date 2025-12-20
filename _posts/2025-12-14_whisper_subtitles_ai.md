

https://www.youtube.com/watch?v=okfw4qXtDVM

https://pypi.org/project/openai-whisper/
openai-whisper 20250625

pip install -U openai-whisper
pip install git+https://github.com/openai/whisper.git 
pip install --upgrade --no-deps --force-reinstall git+https://github.com/openai/whisper.git


pip install setuptools-rust




madon@toshibalex:~ $ pip install -U openai-whisper
Defaulting to user installation because normal site-packages is not writeable
Collecting openai-whisper
  Downloading openai_whisper-20250625.tar.gz (803 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 803.2/803.2 kB 7.4 MB/s eta 0:00:00
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
Requirement already satisfied: more-itertools in ./.local/lib/python3.11/site-packages (from openai-whisper) (5.0.0)
Collecting numba
  Downloading numba-0.63.1-cp311-cp311-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (3.7 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.7/3.7 MB 16.2 MB/s eta 0:00:00
Requirement already satisfied: numpy in ./.local/lib/python3.11/site-packages (from openai-whisper) (1.26.4)
Collecting tiktoken
  Downloading tiktoken-0.12.0-cp311-cp311-manylinux_2_28_x86_64.whl (1.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.2/1.2 MB 20.8 MB/s eta 0:00:00
Collecting torch
  Downloading torch-2.9.1-cp311-cp311-manylinux_2_28_x86_64.whl (899.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 899.8/899.8 MB 1.9 MB/s eta 0:00:00
Requirement already satisfied: tqdm in /usr/lib/python3/dist-packages (from openai-whisper) (4.64.1)
Collecting triton>=2
  Downloading triton-3.5.1-cp311-cp311-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl (170.4 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 170.4/170.4 MB 10.2 MB/s eta 0:00:00
Requirement already satisfied: six<2.0.0,>=1.0.0 in /usr/lib/python3/dist-packages (from more-itertools->openai-whisper) (1.16.0)
Collecting llvmlite<0.47,>=0.46.0dev0
  Downloading llvmlite-0.46.0-cp311-cp311-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (56.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 56.3/56.3 MB 18.6 MB/s eta 0:00:00
Requirement already satisfied: regex>=2022.1.18 in /usr/lib/python3/dist-packages (from tiktoken->openai-whisper) (2022.10.31)
Requirement already satisfied: requests>=2.26.0 in ./.local/lib/python3.11/site-packages (from tiktoken->openai-whisper) (2.32.3)
Collecting filelock
  Downloading filelock-3.20.0-py3-none-any.whl (16 kB)
Requirement already satisfied: typing-extensions>=4.10.0 in ./.local/lib/python3.11/site-packages (from torch->openai-whisper) (4.12.2)
Collecting sympy>=1.13.3
  Downloading sympy-1.14.0-py3-none-any.whl (6.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.3/6.3 MB 35.6 MB/s eta 0:00:00
Collecting networkx>=2.5.1
  Downloading networkx-3.6.1-py3-none-any.whl (2.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.1/2.1 MB 21.7 MB/s eta 0:00:00
Collecting jinja2
  Downloading jinja2-3.1.6-py3-none-any.whl (134 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 134.9/134.9 kB 18.2 MB/s eta 0:00:00
Collecting fsspec>=0.8.5
  Downloading fsspec-2025.12.0-py3-none-any.whl (201 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 201.4/201.4 kB 19.3 MB/s eta 0:00:00
Collecting nvidia-cuda-nvrtc-cu12==12.8.93
  Downloading nvidia_cuda_nvrtc_cu12-12.8.93-py3-none-manylinux2010_x86_64.manylinux_2_12_x86_64.whl (88.0 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 88.0/88.0 MB 17.1 MB/s eta 0:00:00
Collecting nvidia-cuda-runtime-cu12==12.8.90
  Downloading nvidia_cuda_runtime_cu12-12.8.90-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (954 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 954.8/954.8 kB 33.3 MB/s eta 0:00:00
Collecting nvidia-cuda-cupti-cu12==12.8.90
  Downloading nvidia_cuda_cupti_cu12-12.8.90-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (10.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 10.2/10.2 MB 35.3 MB/s eta 0:00:00
Collecting nvidia-cudnn-cu12==9.10.2.21
  Downloading nvidia_cudnn_cu12-9.10.2.21-py3-none-manylinux_2_27_x86_64.whl (706.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 706.8/706.8 MB 2.5 MB/s eta 0:00:00
Collecting nvidia-cublas-cu12==12.8.4.1
  Downloading nvidia_cublas_cu12-12.8.4.1-py3-none-manylinux_2_27_x86_64.whl (594.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 594.3/594.3 MB 2.5 MB/s eta 0:00:00
Collecting nvidia-cufft-cu12==11.3.3.83
  Downloading nvidia_cufft_cu12-11.3.3.83-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (193.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 193.1/193.1 MB 8.7 MB/s eta 0:00:00
Collecting nvidia-curand-cu12==10.3.9.90
  Downloading nvidia_curand_cu12-10.3.9.90-py3-none-manylinux_2_27_x86_64.whl (63.6 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 63.6/63.6 MB 17.9 MB/s eta 0:00:00
Collecting nvidia-cusolver-cu12==11.7.3.90
  Downloading nvidia_cusolver_cu12-11.7.3.90-py3-none-manylinux_2_27_x86_64.whl (267.5 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 267.5/267.5 MB 5.0 MB/s eta 0:00:00
Collecting nvidia-cusparse-cu12==12.5.8.93
  Downloading nvidia_cusparse_cu12-12.5.8.93-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (288.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 288.2/288.2 MB 4.9 MB/s eta 0:00:00
Collecting nvidia-cusparselt-cu12==0.7.1
  Downloading nvidia_cusparselt_cu12-0.7.1-py3-none-manylinux2014_x86_64.whl (287.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 287.2/287.2 MB 3.2 MB/s eta 0:00:00
Collecting nvidia-nccl-cu12==2.27.5
  Downloading nvidia_nccl_cu12-2.27.5-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (322.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 322.3/322.3 MB 3.7 MB/s eta 0:00:00
Collecting nvidia-nvshmem-cu12==3.3.20
  Downloading nvidia_nvshmem_cu12-3.3.20-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (124.7 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 124.7/124.7 MB 8.2 MB/s eta 0:00:00
Collecting nvidia-nvtx-cu12==12.8.90
  Downloading nvidia_nvtx_cu12-12.8.90-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (89 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 90.0/90.0 kB 14.8 MB/s eta 0:00:00
Collecting nvidia-nvjitlink-cu12==12.8.93
  Downloading nvidia_nvjitlink_cu12-12.8.93-py3-none-manylinux2010_x86_64.manylinux_2_12_x86_64.whl (39.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 39.3/39.3 MB 22.6 MB/s eta 0:00:00
Collecting nvidia-cufile-cu12==1.13.1.3
  Downloading nvidia_cufile_cu12-1.13.1.3-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (1.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.2/1.2 MB 27.5 MB/s eta 0:00:00
Requirement already satisfied: charset-normalizer<4,>=2 in /usr/lib/python3/dist-packages (from requests>=2.26.0->tiktoken->openai-whisper) (3.0.1)
Requirement already satisfied: idna<4,>=2.5 in /usr/lib/python3/dist-packages (from requests>=2.26.0->tiktoken->openai-whisper) (3.3)
Requirement already satisfied: urllib3<3,>=1.21.1 in ./.local/lib/python3.11/site-packages (from requests>=2.26.0->tiktoken->openai-whisper) (1.26.18)
Requirement already satisfied: certifi>=2017.4.17 in /usr/lib/python3/dist-packages (from requests>=2.26.0->tiktoken->openai-whisper) (2022.9.24)
Collecting mpmath<1.4,>=1.1.0
  Using cached mpmath-1.3.0-py3-none-any.whl (536 kB)
Collecting MarkupSafe>=2.0
  Downloading markupsafe-3.0.3-cp311-cp311-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl (22 kB)
Building wheels for collected packages: openai-whisper
  Building wheel for openai-whisper (pyproject.toml) ... done
  Created wheel for openai-whisper: filename=openai_whisper-20250625-py3-none-any.whl size=803979 sha256=286a89f07699d8dea2ee24085325287c1c6c4553d988feaa211616a8aff383d0
  Stored in directory: /home/madon/.cache/pip/wheels/32/d2/9a/801b5cc5b2a1af2e280089b71c326711a682fc1d50ea29d0ed
Successfully built openai-whisper
Installing collected packages: nvidia-cusparselt-cu12, mpmath, triton, sympy, nvidia-nvtx-cu12, nvidia-nvshmem-cu12, nvidia-nvjitlink-cu12, nvidia-nccl-cu12, nvidia-curand-cu12, nvidia-cufile-cu12, nvidia-cuda-runtime-cu12, nvidia-cuda-nvrtc-cu12, nvidia-cuda-cupti-cu12, nvidia-cublas-cu12, networkx, MarkupSafe, llvmlite, fsspec, filelock, tiktoken, nvidia-cusparse-cu12, nvidia-cufft-cu12, nvidia-cudnn-cu12, numba, jinja2, nvidia-cusolver-cu12, torch, openai-whisper


Successfully installed MarkupSafe-3.0.3 filelock-3.20.0 fsspec-2025.12.0 jinja2-3.1.6 llvmlite-0.46.0 mpmath-1.3.0 networkx-3.6.1 numba-0.63.1 nvidia-cublas-cu12-12.8.4.1 nvidia-cuda-cupti-cu12-12.8.90 nvidia-cuda-nvrtc-cu12-12.8.93 nvidia-cuda-runtime-cu12-12.8.90 nvidia-cudnn-cu12-9.10.2.21 nvidia-cufft-cu12-11.3.3.83 nvidia-cufile-cu12-1.13.1.3 nvidia-curand-cu12-10.3.9.90 nvidia-cusolver-cu12-11.7.3.90 nvidia-cusparse-cu12-12.5.8.93 nvidia-cusparselt-cu12-0.7.1 nvidia-nccl-cu12-2.27.5 nvidia-nvjitlink-cu12-12.8.93 nvidia-nvshmem-cu12-3.3.20 nvidia-nvtx-cu12-12.8.90 openai-whisper-20250625 sympy-1.14.0 tiktoken-0.12.0 torch-2.9.1 triton-3.5.1






# help


madon@toshibalex:~/tmp $ whisper --help
usage: whisper [-h] [--model MODEL] [--model_dir MODEL_DIR] [--device DEVICE]
               [--output_dir OUTPUT_DIR]
               [--output_format {txt,vtt,srt,tsv,json,all}]
               [--verbose VERBOSE] [--task {transcribe,translate}]
               [--language {af,am,ar,as,az,ba,be,bg,bn,bo,br,bs,ca,cs,cy,da,de,el,en,es,et,eu,fa,fi,fo,fr,gl,gu,ha,haw,he,hi,hr,ht,hu,hy,id,is,it,ja,jw,ka,kk,km,kn,ko,la,lb,ln,lo,lt,lv,mg,mi,mk,ml,mn,mr,ms,mt,my,ne,nl,nn,no,oc,pa,pl,ps,pt,ro,ru,sa,sd,si,sk,sl,sn,so,sq,sr,su,sv,sw,ta,te,tg,th,tk,tl,tr,tt,uk,ur,uz,vi,yi,yo,yue,zh,Afrikaans,Albanian,Amharic,Arabic,Armenian,Assamese,Azerbaijani,Bashkir,Basque,Belarusian,Bengali,Bosnian,Breton,Bulgarian,Burmese,Cantonese,Castilian,Catalan,Chinese,Croatian,Czech,Danish,Dutch,English,Estonian,Faroese,Finnish,Flemish,French,Galician,Georgian,German,Greek,Gujarati,Haitian,Haitian Creole,Hausa,Hawaiian,Hebrew,Hindi,Hungarian,Icelandic,Indonesian,Italian,Japanese,Javanese,Kannada,Kazakh,Khmer,Korean,Lao,Latin,Latvian,Letzeburgesch,Lingala,Lithuanian,Luxembourgish,Macedonian,Malagasy,Malay,Malayalam,Maltese,Mandarin,Maori,Marathi,Moldavian,Moldovan,Mongolian,Myanmar,Nepali,Norwegian,Nynorsk,Occitan,Panjabi,Pashto,Persian,Polish,Portuguese,Punjabi,Pushto,Romanian,Russian,Sanskrit,Serbian,Shona,Sindhi,Sinhala,Sinhalese,Slovak,Slovenian,Somali,Spanish,Sundanese,Swahili,Swedish,Tagalog,Tajik,Tamil,Tatar,Telugu,Thai,Tibetan,Turkish,Turkmen,Ukrainian,Urdu,Uzbek,Valencian,Vietnamese,Welsh,Yiddish,Yoruba}]
               [--temperature TEMPERATURE] [--best_of BEST_OF]
               [--beam_size BEAM_SIZE] [--patience PATIENCE]
               [--length_penalty LENGTH_PENALTY]
               [--suppress_tokens SUPPRESS_TOKENS]
               [--initial_prompt INITIAL_PROMPT]
               [--carry_initial_prompt CARRY_INITIAL_PROMPT]
               [--condition_on_previous_text CONDITION_ON_PREVIOUS_TEXT]
               [--fp16 FP16]
               [--temperature_increment_on_fallback TEMPERATURE_INCREMENT_ON_FALLBACK]
               [--compression_ratio_threshold COMPRESSION_RATIO_THRESHOLD]
               [--logprob_threshold LOGPROB_THRESHOLD]
               [--no_speech_threshold NO_SPEECH_THRESHOLD]
               [--word_timestamps WORD_TIMESTAMPS]
               [--prepend_punctuations PREPEND_PUNCTUATIONS]
               [--append_punctuations APPEND_PUNCTUATIONS]
               [--highlight_words HIGHLIGHT_WORDS]
               [--max_line_width MAX_LINE_WIDTH]
               [--max_line_count MAX_LINE_COUNT]
               [--max_words_per_line MAX_WORDS_PER_LINE] [--threads THREADS]
               [--clip_timestamps CLIP_TIMESTAMPS]
               [--hallucination_silence_threshold HALLUCINATION_SILENCE_THRESHOLD]
               audio [audio ...]

positional arguments:
  audio                 audio file(s) to transcribe

options:
  -h, --help            show this help message and exit
  --model MODEL         name of the Whisper model to use (default: turbo)
  --model_dir MODEL_DIR
                        the path to save model files; uses ~/.cache/whisper by
                        default (default: None)
  --device DEVICE       device to use for PyTorch inference (default: cpu)
  --output_dir OUTPUT_DIR, -o OUTPUT_DIR
                        directory to save the outputs (default: .)
  --output_format {txt,vtt,srt,tsv,json,all}, -f {txt,vtt,srt,tsv,json,all}
                        format of the output file; if not specified, all
                        available formats will be produced (default: all)
  --verbose VERBOSE     whether to print out the progress and debug messages
                        (default: True)
  --task {transcribe,translate}
                        whether to perform X->X speech recognition
                        ('transcribe') or X->English translation ('translate')
                        (default: transcribe)
  --language {af,am,ar,as,az,ba,be,bg,bn,bo,br,bs,ca,cs,cy,da,de,el,en,es,et,eu,fa,fi,fo,fr,gl,gu,ha,haw,he,hi,hr,ht,hu,hy,id,is,it,ja,jw,ka,kk,km,kn,ko,la,lb,ln,lo,lt,lv,mg,mi,mk,ml,mn,mr,ms,mt,my,ne,nl,nn,no,oc,pa,pl,ps,pt,ro,ru,sa,sd,si,sk,sl,sn,so,sq,sr,su,sv,sw,ta,te,tg,th,tk,tl,tr,tt,uk,ur,uz,vi,yi,yo,yue,zh,Afrikaans,Albanian,Amharic,Arabic,Armenian,Assamese,Azerbaijani,Bashkir,Basque,Belarusian,Bengali,Bosnian,Breton,Bulgarian,Burmese,Cantonese,Castilian,Catalan,Chinese,Croatian,Czech,Danish,Dutch,English,Estonian,Faroese,Finnish,Flemish,French,Galician,Georgian,German,Greek,Gujarati,Haitian,Haitian Creole,Hausa,Hawaiian,Hebrew,Hindi,Hungarian,Icelandic,Indonesian,Italian,Japanese,Javanese,Kannada,Kazakh,Khmer,Korean,Lao,Latin,Latvian,Letzeburgesch,Lingala,Lithuanian,Luxembourgish,Macedonian,Malagasy,Malay,Malayalam,Maltese,Mandarin,Maori,Marathi,Moldavian,Moldovan,Mongolian,Myanmar,Nepali,Norwegian,Nynorsk,Occitan,Panjabi,Pashto,Persian,Polish,Portuguese,Punjabi,Pushto,Romanian,Russian,Sanskrit,Serbian,Shona,Sindhi,Sinhala,Sinhalese,Slovak,Slovenian,Somali,Spanish,Sundanese,Swahili,Swedish,Tagalog,Tajik,Tamil,Tatar,Telugu,Thai,Tibetan,Turkish,Turkmen,Ukrainian,Urdu,Uzbek,Valencian,Vietnamese,Welsh,Yiddish,Yoruba}
                        language spoken in the audio, specify None to perform
                        language detection (default: None)
  --temperature TEMPERATURE
                        temperature to use for sampling (default: 0)
  --best_of BEST_OF     number of candidates when sampling with non-zero
                        temperature (default: 5)
  --beam_size BEAM_SIZE
                        number of beams in beam search, only applicable when
                        temperature is zero (default: 5)
  --patience PATIENCE   optional patience value to use in beam decoding, as in
                        https://arxiv.org/abs/2204.05424, the default (1.0) is
                        equivalent to conventional beam search (default: None)
  --length_penalty LENGTH_PENALTY
                        optional token length penalty coefficient (alpha) as
                        in https://arxiv.org/abs/1609.08144, uses simple
                        length normalization by default (default: None)
  --suppress_tokens SUPPRESS_TOKENS
                        comma-separated list of token ids to suppress during
                        sampling; '-1' will suppress most special characters
                        except common punctuations (default: -1)
  --initial_prompt INITIAL_PROMPT
                        optional text to provide as a prompt for the first
                        window. (default: None)
  --carry_initial_prompt CARRY_INITIAL_PROMPT
                        if True, prepend initial_prompt to every internal
                        decode() call. May reduce the effectiveness of
                        condition_on_previous_text (default: False)
  --condition_on_previous_text CONDITION_ON_PREVIOUS_TEXT
                        if True, provide the previous output of the model as a
                        prompt for the next window; disabling may make the
                        text inconsistent across windows, but the model
                        becomes less prone to getting stuck in a failure loop
                        (default: True)
  --fp16 FP16           whether to perform inference in fp16; True by default
                        (default: True)
  --temperature_increment_on_fallback TEMPERATURE_INCREMENT_ON_FALLBACK
                        temperature to increase when falling back when the
                        decoding fails to meet either of the thresholds below
                        (default: 0.2)
  --compression_ratio_threshold COMPRESSION_RATIO_THRESHOLD
                        if the gzip compression ratio is higher than this
                        value, treat the decoding as failed (default: 2.4)
  --logprob_threshold LOGPROB_THRESHOLD
                        if the average log probability is lower than this
                        value, treat the decoding as failed (default: -1.0)
  --no_speech_threshold NO_SPEECH_THRESHOLD
                        if the probability of the <|nospeech|> token is higher
                        than this value AND the decoding has failed due to
                        `logprob_threshold`, consider the segment as silence
                        (default: 0.6)
  --word_timestamps WORD_TIMESTAMPS
                        (experimental) extract word-level timestamps and
                        refine the results based on them (default: False)
  --prepend_punctuations PREPEND_PUNCTUATIONS
                        if word_timestamps is True, merge these punctuation
                        symbols with the next word (default: "'“¿([{-)
  --append_punctuations APPEND_PUNCTUATIONS
                        if word_timestamps is True, merge these punctuation
                        symbols with the previous word (default:
                        "'.。,，!！?？:：”)]}、)
  --highlight_words HIGHLIGHT_WORDS
                        (requires --word_timestamps True) underline each word
                        as it is spoken in srt and vtt (default: False)
  --max_line_width MAX_LINE_WIDTH
                        (requires --word_timestamps True) the maximum number
                        of characters in a line before breaking the line
                        (default: None)
  --max_line_count MAX_LINE_COUNT
                        (requires --word_timestamps True) the maximum number
                        of lines in a segment (default: None)
  --max_words_per_line MAX_WORDS_PER_LINE
                        (requires --word_timestamps True, no effect with
                        --max_line_width) the maximum number of words in a
                        segment (default: None)
  --threads THREADS     number of threads used by torch for CPU inference;
                        supercedes MKL_NUM_THREADS/OMP_NUM_THREADS (default:
                        0)
  --clip_timestamps CLIP_TIMESTAMPS
                        comma-separated list start,end,start,end,...
                        timestamps (in seconds) of clips to process, where the
                        last end timestamp defaults to the end of the file
                        (default: 0)
  --hallucination_silence_threshold HALLUCINATION_SILENCE_THRESHOLD
                        (requires --word_timestamps True) skip silent periods
                        longer than this threshold (in seconds) when a
                        possible hallucination is detected (default: None)


whisper alko.m4a --model medium --language Polish --output_format srt


whisper alko.m4a --model medium --language Polish --output_format srt
100%|█████████████████████████████████████| 1.42G/1.42G [00:50<00:00, 30.0MiB/s]
/home/madon/.local/lib/python3.11/site-packages/whisper/transcribe.py:132: UserWarning: FP16 is not supported on CPU; using FP32 instead
  warnings.warn("FP16 is not supported on CPU; using FP32 instead")
[00:00.000 --> 00:04.000]  CZEŚĆ CZEŚĆ





 WARNING: The scripts proton and proton-viewer are installed in '/home/madon/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  WARNING: The script tqdm is installed in '/home/madon/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  WARNING: The script isympy is installed in '/home/madon/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  WARNING: The scripts f2py and numpy-config are installed in '/home/madon/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-locat
  
# on MSI desktop

whisper alko.m4a --model large --language Polish --output_format srt
100%|██████████████████████████████████████| 2.88G/2.88G [00:27<00:00, 112MiB/s]

  warnings.warn("FP16 is not supported on CPU; using FP32 instead")

# whisper with gpu

https://stackoverflow.com/questions/75775272/cuda-and-openai-whisper-enforcing-gpu-instead-of-cpu-not-working

 19

You need to make sure that you are installing PyTorch with CUDA support, to actually leverage your GPUs.

    See here for reference documentation: https://pytorch.org/get-started/locally/#with-cuda-1

python3 -m pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

pip3 install torch torchvision --index-url https://download.pytorch.org/whl/cu126


python3 -m pip3 install -U openai-whisper

you can then confirm in Python if CUDA is available

```
import torch
torch.cuda.is_available()
```


When using Whisper, you can directly offload the model to the GPU during initialization. To do so, you have to specify the device parameter in the load_model method

So your corrected code would look like:

model = whisper.load_model(model_size, device="cuda")

You can now call the transcribe function directly, no need to use with torch.cuda.device(device)

Note that you actually do not need to specify the device parameter, Whisper attempts to use CUDA by default if it is present


# pytorch not loaded

https://stackoverflow.com/questions/60987997/why-torch-cuda-is-available-returns-false-even-after-installing-pytorch-with


Your graphics card does not support CUDA 9.0.

Since I've seen a lot of questions that refer to issues like this I'm writing a broad answer on how to check if your system is compatible with CUDA, specifically targeted at using PyTorch with CUDA support. Various circumstance-dependent options for resolving issues are described in the last section of this answer.

The system requirements to use PyTorch with CUDA are as follows:

    Your graphics card must support the required version of CUDA
    Your graphics card driver must support the required version of CUDA
    The PyTorch binaries must be built with support for the compute capability of your graphics card

Note: If you install pre-built binaries (using either pip or conda) then you do not need to install the CUDA toolkit or runtime on your system before installing PyTorch with CUDA support. This is because PyTorch, unless compiled from source, is always delivered with a copy of the CUDA library.



1. How to check if your GPU/graphics card supports a particular CUDA version
============================================================================

First, identify the model of your graphics card.

Before moving forward ensure that you've got an NVIDIA graphics card. AMD and Intel graphics cards do not support CUDA.

NVIDIA doesn't do a great job of providing CUDA compatibility information in a single location. The best resource is probably this section on the CUDA Wikipedia page. To determine which versions of CUDA are supported

https://en.wikipedia.org/wiki/CUDA#GPUs_supported



* Locate your graphics card model in the big table and take note of the compute capability version. For example, the GeForce 820M compute capability is 2.1.
* In the bullet list preceding the table check to see if the required CUDA version is supported by the compute capability of your graphics card. For example, CUDA 9.2 is not supported for compute compatibility 2.1.

```
GA107 [GeForce RTX 3050 8GB]
compute compatibility 8.6 
```

If your card doesn't support the required CUDA version then see the options in section 4 of this answer.

Note: Compute capability refers to the computational features supported by your graphics card. Newer versions of the CUDA library rely on newer hardware features, which is why we need to determine the compute capability in order to determine the supported versions of CUDA.



2. How to check if your GPU/graphics driver supports a particular CUDA version
=========================================

The graphics driver is the software that allows your operating system to communicate with your graphics card. Since CUDA relies on low-level communication with the graphics card you need to have an up-to-date driver in order use the latest versions of CUDA.

First, make sure you have an NVIDIA graphics driver installed on your system. You can acquire the newest driver for your system from NVIDIA's website.
https://www.nvidia.com/en-us/drivers/

If you've installed the latest driver version then your graphics driver probably supports every CUDA version compatible with your graphics card (see section 1). To verify, you can check Table 2 in the CUDA release notes. 
https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html


In rare cases 
https://github.com/pytorch/pytorch/issues/4546#issuecomment-356392237
I've heard of the latest recommended graphics drivers not supporting the latest CUDA releases. You should be able to get around this by installing the CUDA toolkit for the required CUDA version and selecting the option to install compatible drivers, though this usually isn't required.

If you can't, or don't want to upgrade the graphics driver then you can check to see if your current driver supports the specific CUDA version as follows:



On Linux/OS X

Run the following command in a terminal window

nvidia-smi

This should result in something like the following

Sat Apr  4 15:31:57 2020       
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 435.21       Driver Version: 435.21       CUDA Version: 10.1     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  GeForce RTX 206...  Off  | 00000000:01:00.0  On |                  N/A |
|  0%   35C    P8    16W / 175W |    502MiB /  7974MiB |      1%      Default |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|    0      1138      G   /usr/lib/xorg/Xorg                           300MiB |
|    0      2550      G   /usr/bin/compiz                              189MiB |
|    0      5735      G   /usr/lib/firefox/firefox                       5MiB |
|    0      7073      G   /usr/lib/firefox/firefox                       5MiB |
+-----------------------------------------------------------------------------+

Driver Version: ###.## is your graphic driver version. In the example above the driver version is 435.21.

CUDA Version: ##.# is the latest version of CUDA supported by your graphics driver. In the example above the graphics driver supports CUDA 10.1 as well as all compatible CUDA versions before 10.1.

Note: The CUDA Version displayed in this table does not indicate that the CUDA toolkit or runtime are actually installed on your system. This just indicates the latest version of CUDA your graphics driver is compatible with.

To be extra sure that your driver supports the desired CUDA version you can visit Table 2 on the CUDA release notes page.


3. How to check if a particular version of PyTorch is compatible with your GPU/graphics card compute capability
==================================

Even if your graphics card supports the required version of CUDA then it's possible that the pre-compiled PyTorch binaries were not compiled with support for your compute capability. For example, in PyTorch 0.3.1 support for compute capability <= 5.0 was dropped.

First, verify that your graphics card and driver both support the required CUDA version (see Sections 1 and 2 above), the information in this section assumes that this is the case.

The easiest way to check if PyTorch supports your compute capability is to install the desired version of PyTorch with CUDA support and run the following from a python interpreter

>>> import torch
>>> torch.zeros(1).cuda()

If you get an error message that reads

Found GPU0 XXXXX which is of cuda capability #.#.
PyTorch no longer supports this GPU because it is too old.

then that means PyTorch was not compiled with support for your compute capability. If this runs without issue then you should be good to go.

Update If you're installing an old version of PyTorch on a system with a newer GPU then it's possible that the old PyTorch release wasn't compiled with support for your compute capability. Assuming your GPU supports the version of CUDA used by PyTorch, then you should be able to rebuild PyTorch from source with the desired CUDA version or upgrade to a more recent version of PyTorch that was compiled with support for the newer compute capabilities.
4. Conclusion

If your graphics card and driver support the required version of CUDA (section 1 and 2) but the PyTorch binaries don't support your compute capability (section 3) then your options are

    Compile PyTorch from source with support for your compute capability (see here)
    Install PyTorch without CUDA support (CPU-only)
    Install an older version of the PyTorch binaries that support your compute capability (not recommended as PyTorch 0.3.1 is very outdated at this point). AFAIK compute capability older than 3.X has never been supported in the pre-built binaries
    Upgrade your graphics card

If your graphics card doesn't support the required version of CUDA (section 1) then your options are

    Install PyTorch without CUDA support (CPU-only)
    Install an older version of PyTorch that supports a CUDA version supported by your graphics card (still may require compiling from source if the binaries don't support your compute capability)
    Upgrade your graphics card


# video card

root@msi:~# lspci | grep ' VGA ' 
01:00.0 VGA compatible controller: NVIDIA Corporation GA107 [GeForce RTX 3050 8GB] (rev a1)


root@msi:~# lspci  -v -s 01:00.0
01:00.0 VGA compatible controller: NVIDIA Corporation GA107 [GeForce RTX 3050 8GB] (rev a1) (prog-if 00 [VGA controller])
	Subsystem: NVIDIA Corporation GA107 [GeForce RTX 3050 8GB]
	Flags: bus master, fast devsel, latency 0, IRQ 136, IOMMU group 11
	Memory at 80000000 (32-bit, non-prefetchable) [size=16M]
	Memory at 4000000000 (64-bit, prefetchable) [size=8G]
	Memory at 4200000000 (64-bit, prefetchable) [size=32M]
	I/O ports at 5000 [size=128]
	Expansion ROM at 81000000 [disabled] [size=512K]
	Capabilities: [60] Power Management version 3
	Capabilities: [68] MSI: Enable+ Count=1/1 Maskable- 64bit+
	Capabilities: [78] Express Legacy Endpoint, MSI 00
	Capabilities: [b4] Vendor Specific Information: Len=14 <?>
	Capabilities: [100] Virtual Channel
	Capabilities: [250] Latency Tolerance Reporting
	Capabilities: [258] L1 PM Substates
	Capabilities: [128] Power Budgeting <?>
	Capabilities: [420] Advanced Error Reporting
	Capabilities: [600] Vendor Specific Information: ID=0001 Rev=1 Len=024 <?>
	Capabilities: [900] Secondary PCI Express
	Capabilities: [bb0] Physical Resizable BAR
	Capabilities: [c1c] Physical Layer 16.0 GT/s <?>
	Capabilities: [d00] Lane Margining at the Receiver <?>
	Capabilities: [e00] Data Link Feature <?>
	Kernel driver in use: nouveau
	Kernel modules: nouveau



# nvidia driver linux

https://wiki.debian.org/NvidiaGraphicsDrivers

root@msi:~# cat /etc/debian_version 
12.1

root@msi:~# lspci -nn | egrep -i "3d|display|vga"
01:00.0 VGA compatible controller [0300]: NVIDIA Corporation GA107 [GeForce RTX 3050 8GB] [10de:2582] (rev a1)


root@msi:~# nvidia-detect
Detected NVIDIA GPUs:
01:00.0 VGA compatible controller [0300]: NVIDIA Corporation GA107 [GeForce RTX 3050 8GB] [10de:2582] (rev a1)

Checking card:  NVIDIA Corporation GA107 [GeForce RTX 3050 8GB] (rev a1)
Your card is supported by the default drivers.
It is recommended to install the
    nvidia-driver
package.


madon@msi:~/whisper$ uname -a
Linux msi 6.1.0-11-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.38-4 (2023-08-08) x86_64 GNU/Linux


root@msi:~# apt install linux-headers-amd64



https://askubuntu.com/questions/23238/how-can-i-find-what-video-driver-is-in-use-on-my-system
madon@msi:~/whisper$ lspci -nnk | grep -E -i --color 'vga|3d|2d' -A3 | grep 'in use'
	Kernel driver in use: nouveau


 apt install nvidia-driver firmware-misc-nonfree



root@msi:~# dmesg | grep -i nvidi
[    2.369336] input: HDA NVidia HDMI/DP,pcm=3 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input4
[    2.369386] input: HDA NVidia HDMI/DP,pcm=7 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input5
[    2.369428] input: HDA NVidia HDMI/DP,pcm=8 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input6
[    2.370526] input: HDA NVidia HDMI/DP,pcm=9 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input7
[    2.886537] audit: type=1400 audit(1765706336.911:7): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe" pid=453 comm="apparmor_parser"
[    2.886540] audit: type=1400 audit(1765706336.911:8): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe//kmod" pid=453 comm="apparmor_parser"
root@msi:~# dmesg | grep -i nvidi -C8
[    2.284509] mei_me 0000:00:16.0: enabling device (0000 -> 0002)
[    2.296956] iTCO_vendor_support: vendor-support=0
[    2.312208] iTCO_wdt iTCO_wdt: Found a Intel PCH TCO device (Version=6, TCOBASE=0x0400)
[    2.312262] iTCO_wdt iTCO_wdt: initialized. heartbeat=30 sec (nowayout=0)
[    2.348018] snd_hda_intel 0000:00:1f.3: enabling device (0000 -> 0002)
[    2.348339] snd_hda_intel 0000:01:00.1: enabling device (0000 -> 0002)
[    2.348374] snd_hda_intel 0000:01:00.1: Disabling MSI
[    2.348376] snd_hda_intel 0000:01:00.1: Handle vga_switcheroo audio client
[    2.369336] input: HDA NVidia HDMI/DP,pcm=3 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input4
[    2.369386] input: HDA NVidia HDMI/DP,pcm=7 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input5
[    2.369428] input: HDA NVidia HDMI/DP,pcm=8 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input6
[    2.370526] input: HDA NVidia HDMI/DP,pcm=9 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input7
[    2.380641] snd_hda_codec_realtek hdaudioC0D0: autoconfig for ALC897: line_outs=1 (0x14/0x0/0x0/0x0/0x0) type:line
[    2.380645] snd_hda_codec_realtek hdaudioC0D0:    speaker_outs=0 (0x0/0x0/0x0/0x0/0x0)
[    2.380646] snd_hda_codec_realtek hdaudioC0D0:    hp_outs=1 (0x1b/0x0/0x0/0x0/0x0)
[    2.380646] snd_hda_codec_realtek hdaudioC0D0:    mono: mono_out=0x0
[    2.380647] snd_hda_codec_realtek hdaudioC0D0:    inputs:
[    2.380648] snd_hda_codec_realtek hdaudioC0D0:      Rear Mic=0x18
[    2.380648] snd_hda_codec_realtek hdaudioC0D0:      Front Mic=0x19
[    2.380649] snd_hda_codec_realtek hdaudioC0D0:      Line=0x1a
--
[    2.462796] perf uncore: Cannot find matched IMC device.
[    2.462837] perf uncore: Cannot find matched IMC device.
[    2.462872] perf uncore: Cannot find matched IMC device.
[    2.613145] Loading of module with unavailable key is rejected
[    2.620770] Loading of module with unavailable key is rejected
[    2.885801] audit: type=1400 audit(1765706336.911:4): apparmor="STATUS" operation="profile_load" profile="unconfined" name="libreoffice-senddoc" pid=457 comm="apparmor_parser"
[    2.886270] audit: type=1400 audit(1765706336.911:5): apparmor="STATUS" operation="profile_load" profile="unconfined" name="lsb_release" pid=452 comm="apparmor_parser"
[    2.886437] audit: type=1400 audit(1765706336.911:6): apparmor="STATUS" operation="profile_load" profile="unconfined" name="libreoffice-oosplash" pid=456 comm="apparmor_parser"
[    2.886537] audit: type=1400 audit(1765706336.911:7): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe" pid=453 comm="apparmor_parser"
[    2.886540] audit: type=1400 audit(1765706336.911:8): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe//kmod" pid=453 comm="apparmor_parser"
[    2.886903] audit: type=1400 audit(1765706336.911:9): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/bin/man" pid=455 comm="apparmor_parser"
[    2.886906] audit: type=1400 audit(1765706336.911:10): apparmor="STATUS" operation="profile_load" profile="unconfined" name="man_filter" pid=455 comm="apparmor_parser"
[    2.938851] Loading of module with unavailable key is rejected
[    2.954358] RAPL PMU: API unit is 2^-32 Joules, 2 fixed counters, 655360 ms ovfl timer
[    2.954361] RAPL PMU: hw unit of domain pp0-core 2^-14 Joules
[    2.954361] RAPL PMU: hw unit of domain package 2^-14 Joules
[    2.958816] cryptd: max_cpu_qlen set to 1000
[    2.977243] AVX2 version of gcm_enc/dec engaged.
root@msi:~# dmesg | grep -i nvidi -C20
[    1.875459] systemd[1]: Finished systemd-random-seed.service - Load/Save Random Seed.
[    1.875588] systemd[1]: first-boot-complete.target - First Boot Complete was skipped because of an unmet condition check (ConditionFirstBoot=yes).
[    1.878883] ACPI: bus type drm_connector registered
[    1.879996] systemd[1]: Started systemd-journald.service - Journal Service.
[    1.884942] ppdev: user-space parallel port driver
[    1.885155] systemd-journald[314]: Received client request to flush runtime journal.
[    1.888911] parport_pc 00:01: reported by Plug and Play ACPI
[    1.889108] parport0: PC-style at 0x378, irq 5 [PCSPP]
[    1.992739] lp0: using parport0 (interrupt-driven).
[    2.075796] intel_pmc_core INT33A1:00:  initialized
[    2.101198] Adding 1000444k swap on /dev/nvme0n1p3.  Priority:-2 extents:1 across:1000444k SSFS
[    2.102708] input: PC Speaker as /devices/platform/pcspkr/input/input3
[    2.284509] mei_me 0000:00:16.0: enabling device (0000 -> 0002)
[    2.296956] iTCO_vendor_support: vendor-support=0
[    2.312208] iTCO_wdt iTCO_wdt: Found a Intel PCH TCO device (Version=6, TCOBASE=0x0400)
[    2.312262] iTCO_wdt iTCO_wdt: initialized. heartbeat=30 sec (nowayout=0)
[    2.348018] snd_hda_intel 0000:00:1f.3: enabling device (0000 -> 0002)
[    2.348339] snd_hda_intel 0000:01:00.1: enabling device (0000 -> 0002)
[    2.348374] snd_hda_intel 0000:01:00.1: Disabling MSI
[    2.348376] snd_hda_intel 0000:01:00.1: Handle vga_switcheroo audio client
[    2.369336] input: HDA NVidia HDMI/DP,pcm=3 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input4
[    2.369386] input: HDA NVidia HDMI/DP,pcm=7 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input5
[    2.369428] input: HDA NVidia HDMI/DP,pcm=8 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input6
[    2.370526] input: HDA NVidia HDMI/DP,pcm=9 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input7
[    2.380641] snd_hda_codec_realtek hdaudioC0D0: autoconfig for ALC897: line_outs=1 (0x14/0x0/0x0/0x0/0x0) type:line
[    2.380645] snd_hda_codec_realtek hdaudioC0D0:    speaker_outs=0 (0x0/0x0/0x0/0x0/0x0)
[    2.380646] snd_hda_codec_realtek hdaudioC0D0:    hp_outs=1 (0x1b/0x0/0x0/0x0/0x0)
[    2.380646] snd_hda_codec_realtek hdaudioC0D0:    mono: mono_out=0x0
[    2.380647] snd_hda_codec_realtek hdaudioC0D0:    inputs:
[    2.380648] snd_hda_codec_realtek hdaudioC0D0:      Rear Mic=0x18
[    2.380648] snd_hda_codec_realtek hdaudioC0D0:      Front Mic=0x19
[    2.380649] snd_hda_codec_realtek hdaudioC0D0:      Line=0x1a
[    2.399225] input: HDA Intel PCH Rear Mic as /devices/pci0000:00/0000:00:1f.3/sound/card0/input8
[    2.399252] input: HDA Intel PCH Front Mic as /devices/pci0000:00/0000:00:1f.3/sound/card0/input9
[    2.399273] input: HDA Intel PCH Line as /devices/pci0000:00/0000:00:1f.3/sound/card0/input10
[    2.399295] input: HDA Intel PCH Line Out as /devices/pci0000:00/0000:00:1f.3/sound/card0/input11
[    2.399316] input: HDA Intel PCH Front Headphone as /devices/pci0000:00/0000:00:1f.3/sound/card0/input12
[    2.462752] perf uncore: Cannot find matched IMC device.
[    2.462796] perf uncore: Cannot find matched IMC device.
[    2.462837] perf uncore: Cannot find matched IMC device.
[    2.462872] perf uncore: Cannot find matched IMC device.
[    2.613145] Loading of module with unavailable key is rejected
[    2.620770] Loading of module with unavailable key is rejected
[    2.885801] audit: type=1400 audit(1765706336.911:4): apparmor="STATUS" operation="profile_load" profile="unconfined" name="libreoffice-senddoc" pid=457 comm="apparmor_parser"
[    2.886270] audit: type=1400 audit(1765706336.911:5): apparmor="STATUS" operation="profile_load" profile="unconfined" name="lsb_release" pid=452 comm="apparmor_parser"
[    2.886437] audit: type=1400 audit(1765706336.911:6): apparmor="STATUS" operation="profile_load" profile="unconfined" name="libreoffice-oosplash" pid=456 comm="apparmor_parser"
[    2.886537] audit: type=1400 audit(1765706336.911:7): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe" pid=453 comm="apparmor_parser"
[    2.886540] audit: type=1400 audit(1765706336.911:8): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe//kmod" pid=453 comm="apparmor_parser"
[    2.886903] audit: type=1400 audit(1765706336.911:9): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/bin/man" pid=455 comm="apparmor_parser"
[    2.886906] audit: type=1400 audit(1765706336.911:10): apparmor="STATUS" operation="profile_load" profile="unconfined" name="man_filter" pid=455 comm="apparmor_parser"
[    2.938851] Loading of module with unavailable key is rejected
[    2.954358] RAPL PMU: API unit is 2^-32 Joules, 2 fixed counters, 655360 ms ovfl timer
[    2.954361] RAPL PMU: hw unit of domain pp0-core 2^-14 Joules
[    2.954361] RAPL PMU: hw unit of domain package 2^-14 Joules
[    2.958816] cryptd: max_cpu_qlen set to 1000
[    2.977243] AVX2 version of gcm_enc/dec engaged.
[    2.977270] AES CTR mode by8 optimization enabled
[    3.177830] Loading of module with unavailable key is rejected
[    3.246024] intel_rapl_common: Found RAPL domain package
[    3.246031] intel_rapl_common: Found RAPL domain core
[    3.398435] Loading of module with unavailable key is rejected
[    3.561638] NET: Registered PF_QIPCRTR protocol family
[    3.698810] r8169 0000:04:00.0: firmware: direct-loading firmware rtl_nic/rtl8168h-2.fw
[    3.724543] Generic FE-GE Realtek PHY r8169-0-400:00: attached PHY driver (mii_bus:phy_addr=r8169-0-400:00, irq=MAC)
[    3.870865] Lockdown: Xorg: raw io port access is restricted; see man kernel_lockdown.7
[    3.900562] r8169 0000:04:00.0 enp4s0: Link is Down
[    4.006296] Lockdown: Xorg: /dev/mem,kmem,port is restricted; see man kernel_lockdown.7
[    4.006333] Lockdown: Xorg: raw io port access is restricted; see man kernel_lockdown.7


REBOOT

echo "options nvidia-drm modeset=1" >> /etc/modprobe.d/nvidia-options.conf





root@msi:~# dmesg | grep -i nvidia -C 20
[    1.898804] parport_pc 00:01: reported by Plug and Play ACPI
[    1.899001] parport0: PC-style at 0x378, irq 5 [PCSPP]
[    2.005167] lp0: using parport0 (interrupt-driven).
[    2.062011] Adding 1000444k swap on /dev/nvme0n1p3.  Priority:-2 extents:1 across:1000444k SSFS
[    2.090946] intel_pmc_core INT33A1:00:  initialized
[    2.111675] input: PC Speaker as /devices/platform/pcspkr/input/input3
[    2.730966] Loading of module with unavailable key is rejected
[    2.732788] mei_me 0000:00:16.0: enabling device (0000 -> 0002)
[    2.733998] perf uncore: Cannot find matched IMC device.
[    2.734048] perf uncore: Cannot find matched IMC device.
[    2.734097] perf uncore: Cannot find matched IMC device.
[    2.734146] perf uncore: Cannot find matched IMC device.
[    2.734277] Loading of module with unavailable key is rejected
[    2.766351] iTCO_vendor_support: vendor-support=0
[    2.780286] iTCO_wdt iTCO_wdt: Found a Intel PCH TCO device (Version=6, TCOBASE=0x0400)
[    2.780355] iTCO_wdt iTCO_wdt: initialized. heartbeat=30 sec (nowayout=0)
[    2.809883] snd_hda_intel 0000:00:1f.3: enabling device (0000 -> 0002)
[    2.810209] snd_hda_intel 0000:01:00.1: enabling device (0000 -> 0002)
[    2.810299] snd_hda_intel 0000:01:00.1: Disabling MSI
[    2.810302] snd_hda_intel 0000:01:00.1: Handle vga_switcheroo audio client
[    2.830333] input: HDA NVidia HDMI/DP,pcm=3 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input4
[    2.830370] input: HDA NVidia HDMI/DP,pcm=7 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input5
[    2.830390] input: HDA NVidia HDMI/DP,pcm=8 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input6
[    2.830404] input: HDA NVidia HDMI/DP,pcm=9 as /devices/pci0000:00/0000:00:01.0/0000:01:00.1/sound/card1/input7
[    2.840137] snd_hda_codec_realtek hdaudioC0D0: autoconfig for ALC897: line_outs=1 (0x14/0x0/0x0/0x0/0x0) type:line
[    2.840141] snd_hda_codec_realtek hdaudioC0D0:    speaker_outs=0 (0x0/0x0/0x0/0x0/0x0)
[    2.840142] snd_hda_codec_realtek hdaudioC0D0:    hp_outs=1 (0x1b/0x0/0x0/0x0/0x0)
[    2.840143] snd_hda_codec_realtek hdaudioC0D0:    mono: mono_out=0x0
[    2.840144] snd_hda_codec_realtek hdaudioC0D0:    inputs:
[    2.840145] snd_hda_codec_realtek hdaudioC0D0:      Rear Mic=0x18
[    2.840146] snd_hda_codec_realtek hdaudioC0D0:      Front Mic=0x19
[    2.840147] snd_hda_codec_realtek hdaudioC0D0:      Line=0x1a
[    2.858286] input: HDA Intel PCH Rear Mic as /devices/pci0000:00/0000:00:1f.3/sound/card0/input8
[    2.858311] input: HDA Intel PCH Front Mic as /devices/pci0000:00/0000:00:1f.3/sound/card0/input9
[    2.858357] input: HDA Intel PCH Line as /devices/pci0000:00/0000:00:1f.3/sound/card0/input10
[    2.858385] input: HDA Intel PCH Line Out as /devices/pci0000:00/0000:00:1f.3/sound/card0/input11
[    2.858408] input: HDA Intel PCH Front Headphone as /devices/pci0000:00/0000:00:1f.3/sound/card0/input12
[    2.900803] audit: type=1400 audit(1765706785.923:4): apparmor="STATUS" operation="profile_load" profile="unconfined" name="lsb_release" pid=444 comm="apparmor_parser"
[    2.900807] audit: type=1400 audit(1765706785.923:5): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe" pid=445 comm="apparmor_parser"
[    2.900808] audit: type=1400 audit(1765706785.923:6): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe//kmod" pid=445 comm="apparmor_parser"
[    2.900906] audit: type=1400 audit(1765706785.923:7): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/bin/man" pid=447 comm="apparmor_parser"
[    2.900908] audit: type=1400 audit(1765706785.923:8): apparmor="STATUS" operation="profile_load" profile="unconfined" name="man_filter" pid=447 comm="apparmor_parser"
[    2.900910] audit: type=1400 audit(1765706785.923:9): apparmor="STATUS" operation="profile_load" profile="unconfined" name="man_groff" pid=447 comm="apparmor_parser"
[    2.900979] audit: type=1400 audit(1765706785.923:10): apparmor="STATUS" operation="profile_load" profile="unconfined" name="libreoffice-oosplash" pid=448 comm="apparmor_parser"
[    3.114756] Loading of module with unavailable key is rejected
[    3.115008] RAPL PMU: API unit is 2^-32 Joules, 2 fixed counters, 655360 ms ovfl timer
[    3.115009] RAPL PMU: hw unit of domain pp0-core 2^-14 Joules
[    3.115010] RAPL PMU: hw unit of domain package 2^-14 Joules
[    3.119778] cryptd: max_cpu_qlen set to 1000
[    3.134221] AVX2 version of gcm_enc/dec engaged.
[    3.134248] AES CTR mode by8 optimization enabled
[    3.341084] Loading of module with unavailable key is rejected
[    3.464418] intel_rapl_common: Found RAPL domain package
[    3.464440] intel_rapl_common: Found RAPL domain core
[    3.545209] Loading of module with unavailable key is rejected
[    3.720906] NET: Registered PF_QIPCRTR protocol family
[    3.810265] r8169 0000:04:00.0: firmware: direct-loading firmware rtl_nic/rtl8168h-2.fw
[    3.836567] Generic FE-GE Realtek PHY r8169-0-400:00: attached PHY driver (mii_bus:phy_addr=r8169-0-400:00, irq=MAC)
[    3.992032] Lockdown: Xorg: raw io port access is restricted; see man kernel_lockdown.7
[    4.036618] r8169 0000:04:00.0 enp4s0: Link is Down



root@msi:~# uname -a
Linux msi 6.1.0-41-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.158-1 (2025-11-09) x86_64 GNU/Linux



REBOOT



root@msi:~# modprobe nvidia_drm
modprobe: ERROR: could not insert 'nvidia_current': Key was rejected by service
modprobe: ERROR: ../libkmod/libkmod-module.c:1047 command_do() Error running install command 'modprobe -i nvidia-current ' for module nvidia: retcode 1
modprobe: ERROR: could not insert 'nvidia': Invalid argument
modprobe: ERROR: could not insert 'nvidia_current_modeset': Key was rejected by service
modprobe: ERROR: ../libkmod/libkmod-module.c:1047 command_do() Error running install command 'modprobe nvidia ; modprobe -i nvidia-current-modeset ' for module nvidia_modeset: retcode 1
modprobe: ERROR: could not insert 'nvidia_modeset': Invalid argument
modprobe: ERROR: could not insert 'nvidia_current_drm': Key was rejected by service
modprobe: ERROR: ../libkmod/libkmod-module.c:1047 command_do() Error running install command 'modprobe nvidia-modeset ; modprobe -i nvidia-current-drm modeset=1 ' for module nvidia_drm: retcode 1
modprobe: ERROR: could not insert 'nvidia_drm': Invalid argument




root@msi:~# ls /lib/modules/6.1.0-41-amd64/updates/dkms/nvidia-current* -1
/lib/modules/6.1.0-41-amd64/updates/dkms/nvidia-current-drm.ko
/lib/modules/6.1.0-41-amd64/updates/dkms/nvidia-current.ko
/lib/modules/6.1.0-41-amd64/updates/dkms/nvidia-current-modeset.ko
/lib/modules/6.1.0-41-amd64/updates/dkms/nvidia-current-peermem.ko
/lib/modules/6.1.0-41-amd64/updates/dkms/nvidia-current-uvm.ko





root@msi:~# sudo mokutil --sb-state
SecureBoot enabled


root@msi:~# dmesg | grep Secure
[    0.000000] Kernel is locked down from EFI Secure Boot; see man kernel_lockdown.7
[    0.000000] secureboot: Secure boot enabled
[    0.491486] integrity: Loaded X.509 cert 'Debian Secure Boot CA: 6ccece7e4c6c0d1f6149f3dd27dfcc5cbb419ea1'
root@msi:~# dmesg | grep Secure -C3
[    0.000000] efi: EFI v2.80 by American Megatrends
[    0.000000] efi: ACPI=0x78606000 ACPI 2.0=0x78606014 TPMFinalLog=0x785d5000 SMBIOS=0x79675000 SMBIOS 3.0=0x79674000 MEMATTR=0x6ecf7098 ESRT=0x73604918 MOKvar=0x7964d000 RNG=0x78382018 TPMEventLog=0x78379018 
[    0.000000] random: crng init done
[    0.000000] Kernel is locked down from EFI Secure Boot; see man kernel_lockdown.7
[    0.000000] secureboot: Secure boot enabled
[    0.000000] SMBIOS 3.5.0 present.
[    0.000000] DMI: Micro-Star International Co., Ltd. MS-7E02/PRO B760M-P (MS-7E02), BIOS A.10 03/24/2023
[    0.000000] tsc: Detected 3400.000 MHz processor
--
[    0.491090] blacklist: Problem blacklisting hash (-13)
[    0.491105] blacklist: Problem blacklisting hash (-13)
[    0.491406] integrity: Loading X.509 certificate: UEFI:MokListRT (MOKvar table)
[    0.491486] integrity: Loaded X.509 cert 'Debian Secure Boot CA: 6ccece7e4c6c0d1f6149f3dd27dfcc5cbb419ea1'
[    0.491488] ima: Allocated hash algorithm: sha256
[    0.508224] evm: Initialising EVM extended attributes:
[    0.508225] evm: security.selinux


https://wiki.debian.org/SecureBoot#DKMS_and_Secure_Boot


sudo mokutil --import /var/lib/dkms/mok.pub
password: alex


alexmadon


 mokutil --sb-state
SecureBoot enabled


root@msi:~# dmesg | grep Secure
[    0.000000] Kernel is locked down from EFI Secure Boot; see man kernel_lockdown.7
[    0.000000] secureboot: Secure boot enabled
[    0.491486] integrity: Loaded X.509 cert 'Debian Secure Boot CA: 6ccece7e4c6c0d1f6149f3dd27dfcc5cbb419ea1'
root@msi:~# dmesg | grep Secure -C3
[    0.000000] efi: EFI v2.80 by American Megatrends
[    0.000000] efi: ACPI=0x78606000 ACPI 2.0=0x78606014 TPMFinalLog=0x785d5000 SMBIOS=0x79675000 SMBIOS 3.0=0x79674000 MEMATTR=0x6ecf7098 ESRT=0x73604918 MOKvar=0x7964d000 RNG=0x78382018 TPMEventLog=0x78379018 
[    0.000000] random: crng init done
[    0.000000] Kernel is locked down from EFI Secure Boot; see man kernel_lockdown.7
[    0.000000] secureboot: Secure boot enabled
[    0.000000] SMBIOS 3.5.0 present.
[    0.000000] DMI: Micro-Star International Co., Ltd. MS-7E02/PRO B760M-P (MS-7E02), BIOS A.10 03/24/2023
[    0.000000] tsc: Detected 3400.000 MHz processor
--
[    0.491090] blacklist: Problem blacklisting hash (-13)
[    0.491105] blacklist: Problem blacklisting hash (-13)
[    0.491406] integrity: Loading X.509 certificate: UEFI:MokListRT (MOKvar table)
[    0.491486] integrity: Loaded X.509 cert 'Debian Secure Boot CA: 6ccece7e4c6c0d1f6149f3dd27dfcc5cbb419ea1'
[    0.491488] ima: Allocated hash algorithm: sha256
[    0.508224] evm: Initialising EVM extended attributes:
[    0.508225] evm: security.selinux


https://wiki.debian.org/SecureBoot#DKMS_and_Secure_Boot


sudo mokutil --import /var/lib/dkms/mok.pub
password: alex


alexmadon

https://forums.developer.nvidia.com/t/nvidia-drivers-not-working-while-secure-boot-is-enabled-after-updating-to-ubuntu-24-04/305351

https://www.youtube.com/watch?v=MZwDl-tC_WM

# disable secure boot on MSI motherboards



https://www.youtube.com/watch?v=MZwDl-tC_WM
boot in BIOS (type DEL several times while booting)
go to advanced mode
navigate to security (right hand side of page)
security -> secure boot-> disable
ESC, ESC save and exit

reboot and check

root@msi:~# mokutil --sb-state
SecureBoot disabled


root@msi:~# apt-get install nvidia-detect 
nvidia-detect 

It is recommended to install the
    nvidia-driver
	
root@msi:~#  apt install linux-headers-amd64

apt install nvidia-kernel-dkms nvidia-driver firmware-misc-nonfree

.....
Building initial module nvidia-current/550.163.01 for 6.12.57+deb13-amd64
Sign command: /lib/modules/6.12.57+deb13-amd64/build/scripts/sign-file
Signing key: /var/lib/dkms/mok.key
Public certificate (MOK): /var/lib/dkms/mok.pub
Certificate or key are missing, generating self signed certificate for MOK...
....



## reboot

confirm driver is "in use":

```
root@msi:~#  lspci -nnk | grep -E -i --color 'vga|3d|2d' -A3 | grep 'in use'
	Kernel driver in use: nvidia
```

get information:

```
root@msi:~# nvidia-smi
Sun Dec 14 14:00:22 2025       
+-----------------------------------------------------------------------------------------+
| NVIDIA-SMI 550.163.01             Driver Version: 550.163.01     CUDA Version: 12.4     |
|-----------------------------------------+------------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
|                                         |                        |               MIG M. |
|=========================================+========================+======================|
|   0  NVIDIA GeForce RTX 3050        On  |   00000000:01:00.0  On |                  N/A |
|  0%   27C    P8             N/A /  115W |      40MiB /   8192MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+
                                                                                         
+-----------------------------------------------------------------------------------------+
| Processes:                                                                              |
|  GPU   GI   CI        PID   Type   Process name                              GPU Memory |
|        ID   ID                                                               Usage      |
|=========================================================================================|
|    0   N/A  N/A       950      G   /usr/lib/xorg/Xorg                             35MiB |
+-----------------------------------------------------------------------------------------+
```


apt-get install pip


```
cat ~/.config/pip/pip.conf
[global]
break-system-packages = true
```


pip3 install torch torchvision --index-url https://download.pytorch.org/whl/cu126

   ━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  3/29 [triton]  WARNING: The scripts proton and proton-viewer are installed in '/home/madon/.local/bin' which is not on PATH.

modify PATH to include the folder above:

madon@msi:~$ vi .bashrc
madon@msi:~$ source .bashrc


pip3 install -U openai-whisper




```
import torch
torch.cuda.is_available()
```
pip3 install -U openai-whisper



madon@msi:~/tmp$ whisper alko.m4a --model turbo --language Polish --output_format srt
100%|██████████████████████████████████████| 1.51G/1.51G [00:14<00:00, 113MiB/s]




# laptop msi

NVIDIA Quadro P3200 
Architecture	Pascal (2016−2021)	
Nom de code	GP104


vs desktop

GA107 [GeForce RTX 3050 8GB]



https://github.com/gpu-mode/lecture2 
https://github.com/gpu-mode/lectures 
https://www.amazon.com/Programming-Massively-Parallel-Processors-Hands/dp/0323912311

Programming Massively Parallel Processors: A Hands-on Approach 4th Edition
by Wen-mei W. Hwu (Author), David B. Kirk (Author), Izzat El Hajj (Author) 


https://www.youtube.com/watch?v=nOxKexn3iBo&t=1239s
 Getting Started With CUDA for Python Programmers 
 
