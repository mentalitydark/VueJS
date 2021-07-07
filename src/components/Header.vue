<template>
    <nav class="navbar is-primary">
        <div class="container">
            <div class="navbar-brand">
                <a href="#" class="navbar-item">Home</a>
                <span class="navbar-burger burger" data-target="navMenu">
                    <span></span>
                    <span></span>
                    <span></span>
                </span>
            </div>
            <div id="navMenu" class="navbar-menu">
                <div class="navbar-end">
                    <a href="#" class="navbar-item">Alimentos</a>
                    <a href="#" class="navbar-item">Calorias</a>
                    <a href="#" class="navbar-item">Quanto consumi</a>
                </div>
            </div>
        </div>
    </nav>
</template>

<script>

</script>

<style>

    #navMenu {
        text-align: right;
    }
    .navbar-item {
        transition: 0.3s;
    }
    @media screen and (max-width: 1023px){
        #navMenu {
            background-color: #00d1b2;
            animation-duration: 0.5s;
            animation-delay: 0s;
            animation-name: navbar-move;
        }
        #navMenu a {
            color: #fff!important;
            font-weight: bold;
        }
        .is-active{
            float: right;
            position: absolute;
            right: 0px;
        }
    }
    @keyframes navbar-move {
        0% {
            position: absolute;
            right: -200px;
            z-index: -1;
        }
        100%{
            position: absolute;
            right: 0px;
            z-index: 1;
        }
    }
</style>