
<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/zenmetsu/artemis">
    <img src="images/artemis_logo.png" alt="Logo" width="180" height="180">
  </a>

<h3 align="center">artemis</h3>

  <p align="center">
    An Apollo program inspired Jeep CJ-5 build
    <br />
    <br />
    <a href="https://github.com/zenmetsu/artemis"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/zenmetsu/artemis">View Demo</a>
    ·
    <a href="https://github.com/zenmetsu/artemis/issues">Report Bug</a>
    ·
    <a href="https://github.com/zenmetsu/artemis/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project
  <a href="https://github.com/zenmetsu/artemis">
    <img src="images/console01.jpg" alt="Logo" width="180" height="180">
  </a>

This project will encompass the transformation of my 1965 CJ-5 to something unique from the period.  In deciding upon a new dashboard layout, I wanted to do something unusual which would showcase the many skills that I have learned over a lifetime of tinkering and creating.  I have long had a fascination with the great space race, and I felt that an aerospace aesthetic would suit this vehicle well.  As such, I have decided to theme my dashboard in a manner reminiscent of the control consoles of the Apollo program.  

## Instrumentation
This project will require me to build many of my own custom gauges:  

#### FDAI
I plan on building my own flight director attitude indicator (FDAI). The original units could drive the ball in pitch and yaw, but roll was indicated by an arrow marker which moved around the outer perimeter.  My FDAI will be completely driven via 3 micro stepper motors and will have a multitude of modes that it can operate in.  Of these:
* traditional pitch/yaw + roll marker
* full pitch/yaw/roll (basically a ball compass)
* full target mode (zeros indicate vehicle pointed at destination in 3-space)
* navigation mode (pitch/yaw/roll with deltas from locked target shown via the 3 error bars)
* orbital mode (ball remains fixed to earth, polar axis and rotation)

#### DSKY
I will need to build a custom DiSplay/KeYboard (DSKY) unit.  I am well aware of the opensource DSKY unit, but the cost of the unit cannot be justified, especially considering that my DSKY will need to control many vehicle functions via GPIO which would require significant modifications to the opensource model.  I am unhappy with the looks of using 7-segment LED units, so I would prefer to homebrew something to give the high contrast and crisp display of the original electroluminescent modules.  I will attempt to follow the excellent project that <a href="https://www.youtube.com/@AppliedScience">Applied Science</a> posted on youtube here:
<a href="https://www.youtube.com/watch?feature=player_embedded&v=v=Z2o_Sp2-aBo" target="_blank">
 <img src="https://img.youtube.com/vi/Z2o_Sp2-aBo/0.jpg" alt="Watch the video" width="240" height="180" border="10" />
</a>

Thanks to the advancement in computing over the past 50 years, my DSKY will host an internal computer in the form of a microcontroller.  I am still in the process of selecting a candidate, but it will likely be an STM32 or RISC-V part. 
The unit will have the following functions:
* program modes similar to the original
    *  0 - Idle
    *  1 - Ignition
    *  6 - Shutdown
    * 12 - Cruise
    * 20 - Navigation
    * 21 - GPS location , ball shows LAT/LONG, LAT/LONG/ALT shown on display in monitor mode
    * 51 - Align ball to earth's axis
    * 52 - IMU align
    * 57 - Align ball to moon's axis
    *  ? - Diagnostics  
* automated control of various systems, with ability to override via keyboard commands or switches on the dash
    * cooling fan
    * starter motor 
    * ignition coil power
    * aux fuel pump
    * lighting (light sensor actuated)
    * comms
        * APRS beaconing
        * js8call message relay 

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

* [![C++][-C++]][-C++-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ROADMAP -->
## Roadmap

- [ ] repaint Jeep body
    - [x] [select paint to match original tone](log/paint/readme.md)
- [ ] build dashboard
    - [ ] build custom gauges
        - [ ] linear style vertical gauges
        - [ ] FDAI
        - [ ] DSKY
    - [ ] decide upon layout
    - [ ] have custom dash panel fabricated
    - [ ] integrate gauges
- [ ] program DSKY
- [ ] expand DSKY functionality
    - [ ] navigation
    - [ ] amateur radio interface
        - [ ] APRS integration
        - [ ] js8call integration

See the [open issues](https://github.com/zenmetsu/artemis/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are welcome.  I have many challenges ahead of me, but I do have ideas on how to tackle some of the problems in a novel manner.  I would love to shortcut the designing of the gauges... if functional replicas of the FDAI or other instrumentation exist, I would enjoy hearing about it so I don't have to reinvent the wheel, so to speak.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Arrow Westervelt - arrow.westervelt@protonmail.com

Project Link: [https://github.com/zenmetsu/artemis](https://github.com/zenmetsu/artemis)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

coming soon... maybe if i get hardware donations or folks willing to sell me flight hardware they can wind up here.  :')
* []()
* []()
* []()

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/github_username/repo_name.svg?style=for-the-badge
[contributors-url]: https://github.com/github_username/repo_name/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/github_username/repo_name.svg?style=for-the-badge
[forks-url]: https://github.com/github_username/repo_name/network/members
[stars-shield]: https://img.shields.io/github/stars/github_username/repo_name.svg?style=for-the-badge
[stars-url]: https://github.com/github_username/repo_name/stargazers
[issues-shield]: https://img.shields.io/github/issues/github_username/repo_name.svg?style=for-the-badge
[issues-url]: https://github.com/github_username/repo_name/issues
[license-shield]: https://img.shields.io/github/license/github_username/repo_name.svg?style=for-the-badge
[license-url]: https://github.com/github_username/repo_name/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/linkedin_username
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[-C++]: https://img.shields.io/badge/-c++-black?logo=c%2B%2B&style=social
[-C++-url]: https://isocpp.org
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
[AppSci]: https://yt3.ggpht.com/ytc/AMLnZu_Yqmn0KqBrnuOqNmBmuik57gD2n1T-TfxqAhNa=s176-c-k-c0x00ffffff-no-rj
[AppSci-url]: https://www.youtube.com/@AppliedScience
