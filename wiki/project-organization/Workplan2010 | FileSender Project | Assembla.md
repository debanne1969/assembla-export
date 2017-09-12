0. Ship version 1.0 release.
   *fix security audit issues
   *fix bugs
   *include remaining crucial features

1. HTML 5.0 UI prototype: Create a HTML 5.0 prototype of the FileSender front end.  Background is the impending halt in development of Google Gears in favour of HTML 5.0: [http://www.pcmag.com/article2/0,2817,2356492,00.asp] (http://www.pcmag.com/article2/0,2817,2356492,00.asp).  Note that the Gears plug in will be maintained for a while to come, but we have to prepare for its demise.  A HTML 5.0 front end could also do without Flash possibly removing our dependency on any plugins. (change this in a more positive wording: HTML 5.0 seems the way to go :)

2. Move administrative UI in PHP: Currently the administrative functions are implemented in the Flash UI.  Moving these to PHP disconnects the administrative UI from the end-user UI and rids us of the requirement to have Flash to access the administrative UI.  This move will allow us to easily connect multiple end-user UIs to the backend without affecting the administrative UI.

3. Allow for multiple storage backends, including Amazon S3 for overflow (ticket #46)

4. UI improvements:
    * multiple file upload (ticket #47)
    * adding new recipients to existing download (ticket #62)
    * enable file management for uploaders (ticket #6)
    * upload speed indicator (ticket #92)
    * Parallellise upload/download (ticket #100)

5. Investigate and implement scalability and resiliency
   * Investigate how to allow the FileSender platform to scale to 100.000s of users and implement the necessary features
   * Investigate how to establish a resilient FileSender installation and
   * implement the necessary features

6. Investigate and implement virtual organisation support.  Through the Geant3 project support for virtual organisations will be
    added to identity federations.
   * Investigate how support for this new functionality in identity federations can be leveraged in FileSender
   * Implement the possible features

7. Investigate client-side encryption option with HTML5.0 UI.  We have had a desire to allow for client-side encryption of transferred files but in our current implementation this proved to be prohibitively unpractical.  When the HTML5.0 prototype is working we will investigate whether client-side encryption would be practically conveivable  in that UI.

