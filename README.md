# Video Player Documentation


## Updates
Dependencies 
  - VueRouter
  - tailwindCSS
  - vue-plyr 
  - vue3

Replaced default html player with vue-plyr(plyr.io)

Added a dockerfile.

Added different video types and support for track.

## Reading
  - https://web.dev/fast/

  - https://medium.com/@inverita/frontend-optimization-8-tips-to-improve-web-performance-29af4b00efe7

  - https://www.smashingmagazine.com/2021/02/optimizing-video-size-quality/

  - https://hackernoon.com/how-to-best-optimize-your-videos-for-the-web-a-quick-guide-492k31bh

  - https://aws.amazon.com/blogs/compute/uploading-to-amazon-s3-directly-from-a-web-or-mobile-application/

  - https://cloud.google.com/storage/docs/uploading-objects#rest-upload-objects 

## Mockup

### Initial Mockup in figma
Home
![alt text](/doc/figmascreenshots/videohome.png)
Player
![alt text](/doc/figmascreenshots/videoplayer.png)
Upload
![alt text](/doc/figmascreenshots/uploadvideo.png)

### New feature design
![alt text](/doc/design.png)

## Timeline (2 weeks)
- ## Week 1
  - Create Initial Mockups
  - Research Requirements and existing implementaions.
  - Build a prototype
  - Showcase the prototype
  - Get Feedback
  - Adjust changes for week 2
- ## Week 2 
  (Might change based on feedback)
  - Create mockup for backend service architecture for new video player service.
  - Integrate new services with last weeks prototype.
  - Migrate work from prototype to existing frontend client.
  - Mock and Test the video player funtionality with updated frontend client.
  - Add Revisions and Documention.
  - Plan a release.

### Building Proof of concept 
What does this feature bring?
- Let users browse existing videos and upload new ones.
- Let users share public links for the video they are currently viewing.
- Commenting on videos for users to share their experince.
- Total views of a video so that users can find popular videos amoung the community

Initial requirements:
Frontend:
- Vue3 and its dependencies.
- Vue router for navigation.
- For video playback 
  - Currently using default html5 video player
  - Future: Replace it with a better video player library such as [video.js](https://github.com/videojs/video.js)
- For video data i am currently using [testVideos.js](/src/testVideos.js) which links to some videos from archive.org.
- User Interface layout
  - Pages: 
    - Home
    - Upload Video
    - User
    - Player
  - Common Components for navigation
    - Home Button
    - Upload Button
    - User Button
  - Components for Player 
    - Video Player
    - Views Count
    - Comments (Old comments) (Log in for new comments)
    - Video Information
    - Share Public URL
   - Components for Home
     - Video gallery
   - Components for Upload Video
     - Choose file
     - Title
     - Description
     - Submit Button
   - Components for User Page
     - Basic User Info (email, name)
     - Sign Out Button


## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
