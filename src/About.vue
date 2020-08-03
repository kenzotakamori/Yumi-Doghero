<template>
    <section id="app-about">
        <h1>About</h1>
        <div class="container animatedParent">
            <div class="about-yumi animated bounceInUp">
                <img src='/src/assets/images/profile.jpg'>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas bibendum libero nec massa luctus lacinia. Sed vel elit vitae tortor hendrerit tincidunt. Fusce a libero eu purus consectetur congue nec ac nisi. Sed lorem nunc, tempor non elit vitae, feugiat elementum elit. Etiam gravida dui vitae leo vehicula cursus. Praesent gravida arcu ac elit bibendum, ac pretium libero pharetra. Cras vitae dui ante. Morbi eget cursus leo. Curabitur auctor orci a justo feugiat, et dapibus orci accumsan. Morbi facilisis metus vitae enim sagittis cursus. Quisque bibendum magna a tellus rutrum, eget tincidunt sapien varius.
                </p>
            </div>
            <div class="about-place">
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas bibendum libero nec massa luctus lacinia. Sed vel elit vitae tortor hendrerit tincidunt. Fusce a libero eu purus consectetur congue nec ac nisi. Sed lorem nunc, tempor non elit vitae, feugiat elementum elit. Etiam gravida dui vitae leo vehicula cursus. Praesent gravida arcu ac elit bibendum, ac pretium libero pharetra. Cras vitae dui ante. Morbi eget cursus leo. Curabitur auctor orci a justo feugiat, et dapibus orci accumsan. Morbi facilisis metus vitae enim sagittis cursus. Quisque bibendum magna a tellus rutrum, eget tincidunt sapien varius.
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
        max-height: 300px;
        border-radius: 100px;
        border: 1px solid #ff3333;
    }
    
</style>