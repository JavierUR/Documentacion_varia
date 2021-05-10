# Trim video

With `ffmpeg`

## Define start and end
* `ffmpeg -i <input> -ss <hh>:<mm>:<ss> -to <hh>:<mm>:<ss> -c:v copy -c:a copy <output>`

Example `ffmpeg -i 06_05_2021_17_27.avi -ss 00:02:24 -to 00:03:23 -c:v copy -c:a copy out.avi`

## Define start and duration
* `ffmpeg -i <input> -ss <hh>:<mm>:<ss> -t <hh>:<mm>:<ss> -c:v copy -c:a copy <output>`

Example `ffmpeg -i 06_05_2021_17_27.avi -ss 00:02:24 -t 00:00:59 -c:v copy -c:a copy out.avi`



### Source
https://www.arj.no/2018/05/18/trimvideo/
