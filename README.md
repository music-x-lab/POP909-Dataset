# POP909 Dataset for Music Arrangement Generation
This is the dataset repository for the paper: [POP909: A Pop-song Dataset for Music Arrangement Generation](https://arxiv.org/abs/2008.07142), in ISMIR 2020.

## Dataset Zip File Structure
* index.xlsx: it contains a list describing the baisc information of each index folder/file (name, number of beats per measure, number of quavers per measure, and modify times)
  
* index folder: it contains several files for a data in the POP909 dataset:
 * index.mid: the music midi file of the arrangement song (MELODY track for the main melody, BRIDGE track for the sub-melody, and PIANO track for the accompaniment)
 * beat_audio/beat_midi.txt: the extracted beat information from the raw audio/midi, the first column is the time (in sec), and the seconcd column is the beat order
 * chord_audio/beat_audio.txt: the extracted chord information from the raw audio/midi, the first/second column is the start/end time (in sec), and the third column is the chord name
 * key_audio.txt: the extracted key change information from the raw audio, the first/second column is the start/end time (in sec), and the third column is the key change.
 * versions folder: it contains different versions of the same arrangement song.

## Data Processing Script
We also provide scripts for the data processing. It will allow you to quickly process the POP909 Files (Midi) into the Google Magenta's music representation as like [Music Transformer](https://magenta.tensorflow.org/music-transformer) and [Performance RNN](https://magenta.tensorflow.org/performance-rnn).
* data_process.ipynb: follow this jupyter notebook, you will get the data input tokens that are able to be fed into the pytorch/tensorflow dataset/dataloader.
(Notice that the representation of encoding the midi sequence are various {e.g., monophonic note tokens, magenta's event tokens, pianoroll, etcs}. We highly recommend users to create their own data processing files to encode the data in their wanted format)
* pop-pickle.zip: it contains the pickle file, already in magenta's event tokens representation

## Credit
Please cite this work if you want to use this dataset

> @inproceedings{pop909-ismir2020, <br>
>  &nbsp;&nbsp;&nbsp;&nbsp;author    = {Ziyu Wang* and Ke Chen* and Junyan Jiang and Yiyi Zhang and Maoran Xu and Shuqi Dai and Guxian Bin and Gus Xia}, <br>
>  &nbsp;&nbsp;&nbsp;&nbsp;title     = {POP909: A Pop-song Dataset for Music Arrangement Generation}, <br>
>  &nbsp;&nbsp;&nbsp;&nbsp;booktitle = {Proceedings of 21st International Conference on Music Information Retrieval, {ISMIR}}, <br>
>  &nbsp;&nbsp;&nbsp;&nbsp;year      = {2020}<br>
> }<br>
