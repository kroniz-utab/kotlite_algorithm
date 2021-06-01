<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Thanks again! Now go create something AMAZING! :D
***
***
***
*** To avoid retyping too much info. Do a search and replace for the following:
*** github_username, repo_name, twitter_handle, email, project_title, project_description
-->

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="#">
    <img src="assets/kotlite_logo.png" alt="kotliteLogo" height="150">
  </a>

  <p align="center">
    <img src="https://img.shields.io/badge/Team-Brillante-9e83fc">
    <img src="https://img.shields.io/badge/ID-BA21_CAP0176-9e83fc?">
  </p>

  <h3 align="center">Kotlite (Angkot Elite) Matching Algorithm</h3>

  <p align="center">
    A Part of Kotlite Ridesharing Application
    <br />
    <a href="#"><strong>Explore the Projects »</strong></a>
    <br />
    <br />
    <!-- <a href="https://github.com/github_username/repo_name">Download Apk</a>
    · -->
    <a href="https://github.com/kroniz-utab/kotlite_algorithm/issues">Report Bug</a>
    ·
    <a href="https://github.com/kroniz-utab/kotlite_algorithm/issues">Request Feature</a>
  </p>
</p>

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#dataset">Dataset</a></li>
    <li><a href="#source">Source</a></li>
    <li>
      <a href="#dataset">Algorithm Explanation</a>
      <ul>
        <li><a href="#location-based-filtering">Location-based Filtering</a></li>
        <li><a href="#similar-direction-approach">Similar Direction Approach</a></li>
        <li><a href="#pickup-time-filtering">Pickup Time Filtering</a></li>
        <li><a href="#distance-based-filtering">Distance-based Filtering</a></li>
      </ul>    
    </li>
    <li><a href="#result-of-testing">Result of Testing</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->

## About The Project

Kotlite is here as a breakthrough idea that answers the need of users to find drivers or passengers from and going to the same routes. It is designed to optimistically accelerate the transformation of the citizens' lifestyle to rideshare and network, eliminating incurable rush hour traffic and provide practicality for user's mobility from one place to another.

<!-- ini bagian teknisnya -->

Kami menggunakan pendekatan Machine Learning untuk memberikan penumpang, rekomendasi driver yang memiliki jalur yang sama. Dengan menggunakan sistem rekomendasi yang kami buat, sistem akan memberikan penumpang rekomendasi driver yang akan melakukan perjalanan yang melewati lokasi pickup penumpang serta melewati atau menuju lokasi dropoff penumpang. Pada sistem rekomendasi ini, kami menggunakan pendekatan location-based filtering, similar direction approaching, pickup time filtering, dan distance-based filtering.

### Built With

- [Tensorflow](https://www.tensorflow.org/)
- [Pandas](https://pandas.pydata.org/)
- [Google Colab](https://colab.research.google.com/) or [Jupyter Notebook](https://jupyter.org/)
- [Google Maps Services Python](https://github.com/googlemaps/google-maps-services-python)

<!-- GETTING STARTED -->

## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

this project requires several resources to be prepared and installed on the local computer, including:

- [Python Virtual Environtment](https://www.python.org/downloads/) (recommendation)
- [Python ver 3.6.x - 3.8.x](https://www.python.org/downloads/) (we use python version 3.8.5)
- [Google Maps API Key](https://developers.google.com/maps)

### Installation

1. Clone the repository

   ```sh
   $ git clone https://github.com/kroniz-utab/kotlite_algorithm.git

   # cd to the repository folder
   $ cd kotlite_algorithm
   ```

2. Install the required environment with virtualenv **(recommendation)**. This part is for run on local computer

   - Linux/macOs
     ```sh
     $ virtualenv env
     $ source env/bin/activate
     (venv) $ pip install -r requirements.txt
     ```
   - Windows
     ```sh
     python -m venv env
     env\scripts\activate
     pip install -r requirements.txt
     ```

3. For local computer you can run this project using jupyter notebook by this way in your CLI

   ```sh
   $ jupyter notebook
   ```

4. Setup `Maps API`, if you found `API KEY` on notebook, change it by your Google Maps API Key.

5. And you can explore how our algorithm was built.

<!-- USAGE EXAMPLES -->

## Dataset

- [NYC Trip Distance Matrix](https://www.kaggle.com/debanjanpaul/new-york-city-taxi-trip-distance-matrix)
- [KWB Dummy Taxi Dataset](https://raw.githubusercontent.com/kroniz-utab/kotlite_algorithm/master/datasets/kotlite_driver_dataset_KWB_with_ket.csv)

  Dataset KWB Dummy Taxi Dataset kami gunakan untuk melakukan testing terhadap algoritma yang kami gunakan. Kami membuat dataset ini karena kami merasa data yang ada pada dataset NYC Trip Distance matrix masih sangat kurang untuk mendukung sistem kami. sehingga kami membuat dataset kami sendiri untuk mendapatkan data yang kami inginkan.

## Source

- [Ridesharing Matching Algorithm](https://www.sciencedirect.com/science/article/pii/S2352146516308730)
- [Lyft Matchmaking](https://eng.lyft.com/matchmaking-in-lyft-line-9c2635fe62c4#.tac6tkgo7)
- [link jurnal 3]()

## Algorithm Explanation

Sistem rekomendasi kami bekerja dengan menggunakan berbagai macam pendekatan untuk mendapatkan hasil rekomendasi yang paling baik menurut kami. Tujuan dari sistem rekomendasi ini adalah untuk mendapatkan driver yang paling mirip tujuan, arah, dan rute. Sistem rekomendasi kami menggunakan basis Nearest Neighbor Algorithm. Alasan kami menggunakan nearest neighbor algorithm adalah data yang kami himpun (gather) adalah data realtime atau crowdsourcing, sehingga kami membutuhkan untuk melakukan training terus menerus ketika penumpang menginginkan rekomendasi driver. Alasan inilah yang membuat kami memilih algoritma nearest neighbor untuk sistem kami. Sistem rekomendasi kami tidak hanya mengandalkan algoritma nearest neighbor saja, akan tetapi kami juga melakukan beberapa pendekatan agar penumpang mendapatkan rekomendasi driver yang bagus, serta driver tidak harus menempuh jarak yang terlalu jauh untuk menjemput atau mengantar penumpang.

### Location-based Filtering

Location-based Filtering merupakan pendekatan paling utama yang kami gunakan. Pendekatan ini menggunakan Algoritma Nearest Neighbour untuk mendeteksi titik rute terdekat dari seluruh data perjalanan driver terhadap titik pickup dan drop off penumpang. Titik terdekat inilah yang akan digunakan untuk pendekatan lainnya.

### Similar Direction Approach

Similar Direction Approach merupakan pendekatan yang kami gunakan untuk menentukan apakah driver memiliki arah perjalanan yang sama. Kami menggunakan driver sequence route data untuk melihat apakah driver berada pada similar direction atau tidak.

### Pickup Time Filtering

Pickup Time Filtering merupakan pendekatan yang kami gunakan untuk memberikan rekomendasi driver kepada penumpang berdasarkan waktu pickup yang diinginkan oleh penumpang. Untuk mendapatkan rekomendasi paling baik kami menggunakan pickup time filtering sebagai salah satu pendekatan dalam sistem rekomendasi kami.

### Distance-based Filtering

Distance-based Filtering adalah proses yang kami gunakan untuk membuat driver kami tidak merasa rugi. Distance-based Filtering digunakan untuk mencari nilai distance dari titik lokasi terdekat driver terhadap titik pickup dan dropoff penumpang. Kami menggunakan pendekatan ini untuk membatasi cakupan jarak yang harus ditempuh oleh pengemudi untuk menjemput dan mengantar penumpang terhadap rute utama yang harusnya ditempuh oleh pengemudi.

## Result of Testing

Kami melakukan test algoritma yang telah kami bangun dengan menggunakan dataset [KWB Dummy Taxi Dataset](https://raw.githubusercontent.com/kroniz-utab/kotlite_algorithm/master/datasets/kotlite_driver_dataset_KWB_with_ket.csv) dengan menggunakan data
passengers who want to depart from MAN 1 Kota Batu on `(-7.8838611,112.5381295)` to GOR Gajah Mada Kota Batu on `(-7.8786821,112.524145)`.

![result pict](assets/result.png)

By using a threshold of 0.7 km from the nearest point, the system recommends 2 drivers who have a similar route, namely the driver with id `[11,19]`. We're trying to see how effective the system is at providing driver recommendations to passengers. in this case we want to test using google maps to see and assess how effective this system is. The testing process uses a scenario that the driver will pick up passengers and then deliver them first before the driver goes to his final destination.

![driver_id 11 routes](assets/driver_11_routes.png)

<p align="center">Gambar rute utama yang seharusnya ditempuh oleh pengemudi dengan id 11</p>

![driver_id 11 with passanger routes](assets/Driver11_with_pass.png)

<p align="center">Gambar rute pengemudi yang harus menjemput dan mengantar penumpang</p>

however, if the driver with ID 11 picks up passengers and delivers them to the passenger's destination, the distance covered will be 12.5 km with an estimated travel time of 28 minutes. It is good enough, that the system can search for and recommend drivers who have the same direction to passengers. The results of the recommendations are also not burdensome or detrimental to drivers, because the maximum pick-up distance is limited to 0.7 Km from the point provided by the maps.

<!-- CONTRIBUTING -->

## Contributing

Feel free to clone, use, and contribute back via [pull request](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests). We'd love to see your pull requests and sent them in! Please use the [issues tracker](https://github.com/kroniz-utab/kotlite_algorithm/issues) to raise bug reports and feature request.

We are excited to see what amazing feature you build in your application using this project. Do ping us at our [contact](#contact) once you build one, feel free to contact us, and we would love to feature your app on our blog.

<!-- LICENSE -->

## License

Distributed under the MIT License. See `LICENSE.md` for more information.

<!-- CONTACT -->

## Contact

_Nanti nyambung ke portal, bikin kata2 kurang lebih jika ingin menghubungi kami silahkan lihat di link berikut_

<!-- ACKNOWLEDGEMENTS -->

## Acknowledgements

<p align="center">
  <img src="assets/bangkit.png" height="200"></img>&nbsp; &nbsp;<img src="assets/brillante_logos.png" height="200">
</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/kroniz-utab/kotlite_algorithm.svg?style=flat
[contributors-url]: https://github.com/kroniz-utab/kotlite_algorithm/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/kroniz-utab/kotlite_algorithm.svg?style=flat
[forks-url]: https://github.com/kroniz-utab/kotlite_algorithm/network/members
[issues-shield]: https://img.shields.io/github/issues/kroniz-utab/kotlite_algorithm.svg?style=flat
[issues-url]: https://github.com/kroniz-utab/kotlite_algorithm/issues
[license-shield]: https://img.shields.io/github/license/kroniz-utab/kotlite_algorithm.svg?style=flat
[license-url]: https://github.com/kroniz-utab/kotlite_algorithm/blob/master/LICENSE.txt

<!-- https://github.com/SVeeIS/kotliteProjectAPI -->
