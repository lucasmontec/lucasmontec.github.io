---

name: InstaCasa AR Viewer
type: Application
featured: false

# Listing settings

font_awesome_icon: fa-mobile

bg: assets/images/instacasa_a.png

direct_link: https://apkpure.com/br/instacasa-realidade-aumentad/com.farm.ideas.arview

one_liner: An augmented reality app for architectural visualization.
description: |
     This is an app that shows 3D house projects that fit various plots of land. The user navigates the client company site, finds the lot specifications
     that match his interest and then he can choose to visualize the house project the client site offers for that plot. When the user clicks to view the
     project, the site opens the app in the phone and the model is loaded and displayed in augmented reality.

# Main site settings

main_image: assets/images/instacasa_c.png

---

### AR Viewer

As we know augmented reality is an important tool for marketing campaigns that can increase their value as well as create a direct channel between brands and clients.
InstaCasa saw this as an opportunity to create an app that improves their client shopping experience by showing how the product fits in the real world. This is a known
and important attribute of this technology, the ability to see virtual assets in real life.

<img src="https://lucasmontec.github.io/assets/images/instacasa_c.png" alt="picture of the application showing the download menu" style="width:40%;display:block;margin:auto;"/>

This experience is really important for the customer, especially when dealing with products that can only be seen in virtual environments. When you give the user the power
of experiencing the product in real life it changes his understanding of it and creates value.

## Features of a good AR App

The application developed for InstaCasa has several nice features that differ from usual augmented reality experiences. The main problem we had is that usually, the final client 
doesn’t want to download any new apps. This problem is recurring for this kind of media and every company deals with it differently. 
We had several options, from developing the app using javascript and deploying it with WebGL, to creating a native app that the user has to download. The app using WebGL would have 
several limitations, the marker would have to have a 2cm black border and a matrix of black squares and/or the content displayed in the virtual space would have to be limited since the 
hardware access would be virtualized. Still, the customer wouldn’t have to install an app which is desired. 

<img src="https://lucasmontec.github.io/assets/images/instacasa_b.png" alt="picture of the application showing the download menu" style="width:40%;display:block;margin:auto;"/>

Another option was to build a small native app that wouldn’t have the 3D models in it and that could be downloaded as an android instant app. An instant app is an app that can be launched 
through a link without installing it on the device. This option would allow us to deploy an app that could handle scanning of any image as a marker and that could render complex 3D scenes 
with native hardware access. This option would also allow us to use the client web site as the interface for the app, which would cut costs and make the development time much shorter. 
We went with the second option but decided later to make the app as a normal application and not an instant app. 

A valuable feature that was added also was the integration with the client backend. Since the app was planned to be light and we would use the client’s site as an interface, it was only 
natural that we decided to not include the 3D projects in the app. Instead, we worked with the client’s backend developers to provide an API where the models would be hosted on their site
directly. The app only reads the URL that was clicked to open it and then it downloads and stores the projects the consumer wants to see.
