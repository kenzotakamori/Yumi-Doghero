<template>
    <section id="app-about">
        <div class="container">
            <h1><span>About</span></h1>
            <div class="about-yumi">
                <img src='/src/assets/images/profile.jpg'>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas bibendum libero nec massa luctus lacinia. Sed vel elit vitae tortor hendrerit tincidunt. Fusce a libero eu purus consectetur congue nec ac nisi. Sed lorem nunc, tempor non elit vitae, feugiat elementum elit. Etiam gravida dui vitae leo vehicula cursus. Praesent gravida arcu ac elit bibendum, ac pretium libero pharetra. Cras vitae dui ante. Morbi eget cursus leo. Curabitur auctor orci a justo feugiat, et dapibus orci accumsan. Morbi facilisis metus vitae enim sagittis cursus. Quisque bibendum magna a tellus rutrum, eget tincidunt sapien varius.
                    Phasellus luctus, nunc at gravida imperdiet, metus metus convallis ligula, sit amet tristique neque arcu eu quam. Aenean pharetra porta turpis. Maecenas eget dictum libero, sed consequat nisi. Fusce aliquet accumsan ultricies. Sed vitae lacus quam. Etiam ut arcu hendrerit, hendrerit dui id, accumsan turpis. Etiam et fringilla enim. Vestibulum bibendum auctor nisi, eget varius diam dignissim eget.
                </p>
            </div>
            <div class="about-place">
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas bibendum libero nec massa luctus lacinia. Sed vel elit vitae tortor hendrerit tincidunt. Fusce a libero eu purus consectetur congue nec ac nisi. Sed lorem nunc, tempor non elit vitae, feugiat elementum elit. Etiam gravida dui vitae leo vehicula cursus. Praesent gravida arcu ac elit bibendum, ac pretium libero pharetra. Cras vitae dui ante. Morbi eget cursus leo. Curabitur auctor orci a justo feugiat, et dapibus orci accumsan. Morbi facilisis metus vitae enim sagittis cursus. Quisque bibendum magna a tellus rutrum, eget tincidunt sapien varius.
                    Phasellus luctus, nunc at gravida imperdiet, metus metus convallis ligula, sit amet tristique neque arcu eu quam. Aenean pharetra porta turpis. Maecenas eget dictum libero, sed consequat nisi. Fusce aliquet accumsan ultricies. Sed vitae lacus quam. Etiam ut arcu hendrerit, hendrerit dui id, accumsan turpis. Etiam et fringilla enim. Vestibulum bibendum auctor nisi, eget varius diam dignissim eget.
                </p>
                <img src='/src/assets/images/NATAL11.jpg'>
            </div>
        </div>
    </section>
</template>

<script>
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('aboutLoaded', {
                flag: true
            })            
        },
        data() {
            return {
                imgYumi: 'sdncoids',
                imgPlace: ''
            }
        }    
    }
</script>
<style>
    .about-yumi, .about-place {
        display: inline-flex;
    }

    .about-yumi img, .about-place img {
        max-height: 400px;
        border-radius: 100px;
        border: 1px solid red;
    }
    
</style>