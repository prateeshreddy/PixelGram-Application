# PixelGram Application

The goal is to Build an application to store all user's captured moments and memories in the cloud and retrieve them as and when required. This Application was build along with Sai Prudvi krishna Sannidhi, Sravya Garaga, Suraj Gupta Gudla

## Functional Requirements :
- The user should be able to upload and download their photos.
- The user must be able to log in via various authentication methods like Google, GitHub, and IU login.
- All the photos are being stored in the cloud securely.
- The user should be able to share their photos to other platforms like mail, WhatsApp, etc.
- The user should be able to organize their photos into albums and also enable shared access (either private, group access, or public) to their albums

## High level System Design
It's advantageous to have access to a camera all the time. Everything is captureable. The drawback is that we have no way to save or share all of these pictures. When using various devices to take pictures, our photo-sharing program "PixelGram" makes it the ideal option to store pictures online. PixelGram enables automatic photo backup from a variety of devices and supports bulk image upload. The users can sign in using their GitHub, Google, or Indiana University identities. With the help of this software, users may categorize their photos into albums and folders and tag individual photos with names and locations to make them easier to find. The user's saved photographs will be arranged chronologically. The users can also privately or publicly share an album or set of photographs. The pictures are kept in the cloud and can be retrieved whenever necessary from offline systems. With PixelGram, you can conveniently save and share the moments you've captured online in a safer and more timely manner.

<img src="Files/Napkin diagram.jpeg" width = "800">

## Low level System Design
PixelGram is a micro-service architecture-based application that enables users to upload, download, share and manage images. Through the UI, a user logs in as the end user. ReactJS and Bootstrap are used to build the user interface. The GRPC protocol is used by the front end to communicate with the backend architecture. Since the GRPC web client does not send HTTP2 queries, we use envoy to convert the requests into HTTP2. The GRPC facilitates communication between services as well as between the react client and microservices. The various microservices that we employ include: With the help of the upload/download image service, users can both upload and download images to and from the cloud. The user can share the image data with other PixelGram users thanks to the image service. A user can register and log in to the application using the user service in order to upload, download, and share photographs. There are other third-party login options, including GitHub, Google, and IU. To obtain an image's meta data, such as its location, timestamp, file format, and size, the meta data service is available. The purpose of the session management service is to better secure login by managing the user's session. the database service to establish a connection with the database and perform any necessary actions. Through this service, all other services connect to the database.

<img src="Files/System Design Architecture.jpeg" width = "1000">
