# Using Oracle REST Data Service 

## Configuration - Oracle REST Data Service

### HowTo use an Oracle Resource Handler to query an resource 

HowTo use [offset and limit] in the URL as query parameter on a resource locator.

<h3>[../resource/?offset=250&limit=25]</h3>

```
https://localhost:8443/ords/apex24_rw/youtube/youtube_videos/?offset=250&limit=25
```

REST Response :

```
{
  "items": [
    {
      "id": 251,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Bebop Vocabulary - Make Sure To Use This Powerful Resource",
      "youtube_thump": "https://i.ytimg.com/vi/5dzwLz7Xi3o/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=5dzwLz7Xi3o"
    },
    {
      "id": 252,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "The Truth About Learning Jazz Is Not Scales And Arpeggios",
      "youtube_thump": "https://i.ytimg.com/vi/UkU3Ze8XGMs/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=UkU3Ze8XGMs"
    },
    {
      "id": 253,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "5 Easy Jazz Solo Exercises That You Want To Know",
      "youtube_thump": "https://i.ytimg.com/vi/h4zQjSecjvI/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=h4zQjSecjvI"
    },
    {
      "id": 254,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "5 Magical Apps for Guitar Practice - Super Useful",
      "youtube_thump": "https://i.ytimg.com/vi/U4BQvsn02-Y/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=U4BQvsn02-Y"
    },
    {
      "id": 255,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "The Two Reasons Triads Are Amazing For Jazz Solos",
      "youtube_thump": "https://i.ytimg.com/vi/lB8cfdQBOqE/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=lB8cfdQBOqE"
    },
    {
      "id": 256,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "How To Go From Scales to Great Jazz Phrases",
      "youtube_thump": "https://i.ytimg.com/vi/AvShj4SZMcY/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=AvShj4SZMcY"
    },
    {
      "id": 257,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "The Solos You Want To Learn By Ear To Play better Jazz Guitar",
      "youtube_thump": "https://i.ytimg.com/vi/8wy6CYrw7Vc/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=8wy6CYrw7Vc"
    },
    {
      "id": 258,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Basic Jazz Chord Exercises Everyone Should Know!",
      "youtube_thump": "https://i.ytimg.com/vi/F8fvQI-pgHg/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=F8fvQI-pgHg"
    },
    {
      "id": 259,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "A Simple Jazz Solo Skill You Want To Master",
      "youtube_thump": "https://i.ytimg.com/vi/iki_qdAKxW8/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=iki_qdAKxW8"
    },
    {
      "id": 260,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Alternate Picking - Get The Exercises Right!",
      "youtube_thump": "https://i.ytimg.com/vi/PeIdrmUWw0Q/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=PeIdrmUWw0Q"
    },
    {
      "id": 261,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Bebop Magic - One Of The Best And Most Difficult Things About Jazz",
      "youtube_thump": "https://i.ytimg.com/vi/rueJGCSsGko/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=rueJGCSsGko&pp=0gcJCdMKAYcqIYzv"
    },
    {
      "id": 262,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Chord Melody - 5 Beautiful Methods You Want To Know",
      "youtube_thump": "https://i.ytimg.com/vi/MEg1hsra6GU/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=MEg1hsra6GU"
    },
    {
      "id": 263,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "7 Easy Jazz Standards In Minor You Need To Know",
      "youtube_thump": "https://i.ytimg.com/vi/3bGWISsJLuc/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=3bGWISsJLuc"
    },
    {
      "id": 264,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "The Best Triad Exercises - How To Get The Essentials Right",
      "youtube_thump": "https://i.ytimg.com/vi/Buta15gu64Q/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=Buta15gu64Q"
    },
    {
      "id": 265,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Practice Advice From Chick Corea",
      "youtube_thump": "https://i.ytimg.com/vi/gXcOOV_Wnmk/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=gXcOOV_Wnmk"
    },
    {
      "id": 266,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "The 3 Bebop Licks You Need To Know",
      "youtube_thump": "https://i.ytimg.com/vi/2iFZdLf7a1o/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=2iFZdLf7a1o"
    },
    {
      "id": 267,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "How To Make 4-Chord Vamps That Sound Great",
      "youtube_thump": "https://i.ytimg.com/vi/wJi2d66Cqic/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=wJi2d66Cqic"
    },
    {
      "id": 268,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Great Comping Hack On A Jazz Blues",
      "youtube_thump": "https://i.ytimg.com/vi/2qh51IVUVck/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=2qh51IVUVck"
    },
    {
      "id": 269,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Jazz Beginner Mistakes - How To Learn Scales",
      "youtube_thump": "https://i.ytimg.com/vi/WwB4v6iWOlo/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=WwB4v6iWOlo&pp=0gcJCdMKAYcqIYzv"
    },
    {
      "id": 270,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "The Most Important Melodic Minor Modes In One Song",
      "youtube_thump": "https://i.ytimg.com/vi/RBpagEeInfY/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=RBpagEeInfY"
    },
    {
      "id": 271,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Jazz Blues - You Need To Know Triads!",
      "youtube_thump": "https://i.ytimg.com/vi/b6K2P15UdeI/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=b6K2P15UdeI"
    },
    {
      "id": 272,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Jazz Reharmonization - How To Make Great Variations of a II V I",
      "youtube_thump": "https://i.ytimg.com/vi/8MyWEZ4t_aw/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=8MyWEZ4t_aw"
    },
    {
      "id": 273,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "What Really Makes It Sound Like Jazz?",
      "youtube_thump": "https://i.ytimg.com/vi/ZZUHhEA5qUs/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=ZZUHhEA5qUs"
    },
    {
      "id": 274,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Easy - Jazz Chords - You Want To Know",
      "youtube_thump": "https://i.ytimg.com/vi/fjk2-D2duBo/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=fjk2-D2duBo"
    },
    {
      "id": 275,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "Beautiful Jazz Chords That Make You Less Boring",
      "youtube_thump": "https://i.ytimg.com/vi/FUniOg5yioY/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=FUniOg5yioY"
    }
  ],
  "hasMore": true,
  "limit": 25,
  "offset": 250,
  "count": 25,
  "links": [
    {
      "rel": "self",
      "href": "https://localhost:8443/ords/apex24_rw/youtube/youtube_videos/"
    },
    {
      "rel": "describedby",
      "href": "https://localhost:8443/ords/apex24_rw/metadata-catalog/youtube/youtube_videos/"
    },
    {
      "rel": "first",
      "href": "https://localhost:8443/ords/apex24_rw/youtube/youtube_videos/?limit=25"
    },
    {
      "rel": "next",
      "href": "https://localhost:8443/ords/apex24_rw/youtube/youtube_videos/?offset=275&limit=25"
    },
    {
      "rel": "prev",
      "href": "https://localhost:8443/ords/apex24_rw/youtube/youtube_videos/?offset=225&limit=25"
    }
  ]
}
```

<h3>[../resource/?q={"youtube_title":{"$instr":"phras"}}]</h3>

```
https://localhost:8443/ords/apex24_rw/youtube/youtube_videos/?q={%22youtube_title%22:{%22$instr%22:%22phras%22}}
```
REST Response :

```
{
  "items": [
    {
      "id": 167,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "The 5 Best Bebop Shortcuts To Fix Your Jazz Phrasing",
      "youtube_thump": "https://i.ytimg.com/vi/B6Ml7KWDiPw/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=B6Ml7KWDiPw&pp=0gcJCdMKAYcqIYzv"
    },
    {
      "id": 190,
      "youtube_artist": "Jens Larsen",
      "video_style": "Jazz Guitar Video",
      "youtube_title": "The Real Secret About Chromatic Phrases And Great Jazz Licks",
      "youtube_thump": "https://i.ytimg.com/vi/hzX2cgNOvxA/hqdefault.jpg",
      "youtube_url": "https://www.youtube.com/watch?v=hzX2cgNOvxA"
    }
],
  "hasMore": false,
  "limit": 10000,
  "offset": 0,
  "count": 2,
  "links": [
    {
      "rel": "self",
      "href": "https://localhost:8443/ords/apex24_rw/youtube/youtube_videos/?q=%7B%22youtube_title%22:%7B%22%24instr%22:%22phras%22%7D%7D"
    },
    {
      "rel": "describedby",
      "href": "https://localhost:8443/ords/apex24_rw/metadata-catalog/youtube/youtube_videos/"
    },
    {
      "rel": "first",
      "href": "https://localhost:8443/ords/apex24_rw/youtube/youtube_videos/?q=%7B%22youtube_title%22:%7B%22%24instr%22:%22phras%22%7D%7D"
    }
  ]
}
```
