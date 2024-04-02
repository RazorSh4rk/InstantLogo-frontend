<script>
	import { Carousel } from "flowbite-svelte";
    import barbershop from "$lib/assets/barbershop.png"
    import carshop from "$lib/assets/carshop.png"
    import fish from "$lib/assets/fish.png"
    import petsalon from "$lib/assets/petsalon.png"

    const images = [
        {
            alt: "Barbershop",
            src: barbershop,
            title: "Barbershop"
        },
        {
            alt: "Car tuning garage",
            src: carshop,
            title: "Car tuning garage"
        },
        {
            alt: "Fish bait shop",
            src: fish,
            title: "Fish bait shop"
        },
        {
            alt: "Pet salon",
            src: petsalon,
            title: "Pet salon"
        },
    ]
</script>

<div class="pl-6 pb-10">
    <Carousel {images} duration="3000"></Carousel>
</div>