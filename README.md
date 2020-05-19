# YouTube-video-download-python
Download any video from YouTube using python

#This code do not run on online notebooks as it requires to open up a new tab which is not possible by notebooks
import tkinter as tk
#tkinter is already installed in python 
from pytube import YouTube
#Install pytube3
def downloadVid():
    global E1
    string =E1.get()
    yt = YouTube(str(string))
    videos = yt.streams.first()
    destination=str(input("Enter your destination"))
    #enter the desination where you want to save the video
    videos.download(destination)
    print(yt.title+"\n Ha been downloaded")
root=tk.Tk()

w=tk.Label(root,text="Youtube Downloader")
w.pack()


E1=tk.Entry(root,bd=5)
E1.pack(side=tk.TOP)


button=tk.Button(root,text="Download",fg="red",command=downloadVid   )
button.pack(side=tk.BOTTOM)

root.mainloop()

