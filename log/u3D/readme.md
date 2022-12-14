```                                                          
                                                       _____                                              
                                                      (__  /   /\                                         
                                                 _   _  / /   /  \                                        
                                                | | | |(__ \ / /\ \                                       
                                                | |_| |___) ) /__\ \                                      
                                                | ._,_(____/________\                                     
                                                | |                                                       
                                                |_|
```

# A micro 3D rasterization implementation for embedded projects

## Overview
While I am releasing this under the MIT license, I would hope that no one would attempt to recycle my code for use in another project.  I have no issue with code reuse in general, however doing so goes against the spirit of this endeavor.

I set out to add basic 3D functionality to my project in order to leverage the power of the stm32h743zi that was driving it. I tried for many an hour to do exactly what you as the reader might be attempting to do by reviewing this project... namely attempting to adopt someone else's code to do my bidding.  Truth be told, 3D rasterization is not as much blackmagic as one may suspect... and at its heart the rasterization is agnostic with regard to framebuffer and device interfacing.  Trying to divorce the rasterizer from an existing project to work in your particular case may be more hassle than it is worth.  To that end, I am going to release the full source for my rasterizer, but I am also going to document the steps taken as I undertake the learning process myself.  The hope is that this documentation will help others understand what the code is doing and demystify 3D in general.
