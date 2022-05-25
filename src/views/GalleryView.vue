/* eslint-disable no-mixed-spaces-and-tabs */
<template>
   <div class="gallery">
        <h1 class="heading"> Kayı Memories</h1>
        
        <div class="card-container">

            <div class="card" style="--image: url('/kayi-sanjak.png'); --angle: 5deg; --x: 6%; --y: 7%; --caption: 'Kayı Sanjak'"></div>

            <div class="card" style="--image: url('/inegol.png'); --angle: -1deg; --x: -20%; --y: -20%; --caption: 'İnegöl Castle - 1299'"></div>

            <div class="card" style="--image: url('/bursa.png'); --angle: -14deg; --x: -25%; --y: 0%; --caption: 'Bursa - 1328'"></div>

            <div class="card" style="--image: url('/bazaar.png'); --angle: 7deg; --x: 30%; --y: -7%; --caption: 'Bazaar - 2020'"></div>
            
            <div class="card" style="--image: url('/sogut.png'); --angle: 9deg; --x: 10%; --y: -27%; --caption: 'Sogut - 2020'"></div>

        </div>
    </div>
</template>

<style>
@media (max-width: 1023px) {
    .heading {
        position: absolute;
        bottom: 0;
        right: 0;
        margin: 0.5rem 5vmin;
    }
}
.card-container {
    align-items: center;
    position: relative;
	width: 75vmin;
	height: 80vmin;
}

.card {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgb(206, 253, 235);
	border-radius: 21px;
	box-shadow: 2px 2px 50px rgba(#111, .35);
	transition: transform .35s ease-out;
	transform: translate(var(--x), var(--y)) scale(.35) rotate(var(--angle));
	will-change: transform;
}

.card:hover {
    transform: scale(1) rotate(0deg);
    z-index: 1;
    background-color: #2dffb9;
}

.card:hover::before {
    opacity: 1;
}

.card:before {
	content: "";
	display: block;
	width: 90%;
	height: 80%;
	margin: 5%;
	background: var(--image) center center no-repeat;
	background-size: cover;
	box-shadow: inset 0 0 5px rgba(#222, .35);
	border-radius: 2px;
	filter: sepia(.2) brightness(.9) contrast(1.2);
	transition: opacity .35s ease-out;
	opacity: .5;
	will-change: opacity;
}

.card:after {
	display: block;
	content: var(--caption);
	font-weight: 500;
	color: var(--vt-c-black);
	font-size: 3vmin;
	opacity: .75;
	text-align: center;
}
.gallery {
    text-align: center;
    background-color: #00bd7e;
    border-radius: 15px;
    padding: 50px;
}
@media (min-width: 1024px) {
    .gallery {
        min-height: 100vh;
        display: flex;
        align-items: center;
    }
    .heading {
        position: absolute;
        bottom: 0;
        right: 0;
        margin: 100vmin 5vmin;
    }
}
</style>
