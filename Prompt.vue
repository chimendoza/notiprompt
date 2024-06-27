<template>

    <div class="noti_prompt-dialog">


        <div class="noti_prompt-content">

            <div class="noti_prompt-icon">
                <svg v-if="item.type == 'success'" class="noti_prompt-success" xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 12 12" aria-hidden="true">
                    <path
                        d="M6,-0c-3.308,-0 -6,2.692 -6,6c-0,3.308 2.692,6 6,6c3.308,-0 6,-2.692 6,-6c-0,-3.308 -2.692,-6 -6,-6Zm3.123,3.989l-3.877,4.616c-0.086,0.102 -0.213,0.162 -0.346,0.164l-0.008,0c-0.131,0 -0.256,-0.055 -0.343,-0.153l-1.662,-1.846c-0.081,-0.085 -0.126,-0.199 -0.126,-0.316c0,-0.254 0.209,-0.462 0.462,-0.462c0.135,0 0.263,0.059 0.35,0.161l1.307,1.451l3.536,-4.209c0.087,-0.101 0.215,-0.159 0.349,-0.159c0.253,-0 0.461,0.208 0.461,0.461c0,0.107 -0.036,0.21 -0.103,0.292Z">
                    </path>
                </svg>
                <svg v-if="item.type == 'info'" class="noti_prompt-info" xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 12 12" aria-hidden="true" fill="currentColor">
                    <path
                        d="M6,0c-3.308,0 -6,2.692 -6,6c0,3.308 2.692,6 6,6c3.308,0 6,-2.692 6,-6c0,-3.308 -2.692,-6 -6,-6Zm0,2.46c0.428,0 0.78,0.352 0.78,0.78c-0,0.428 -0.352,0.78 -0.78,0.78c-0.428,0 -0.78,-0.352 -0.78,-0.78c0,-0.428 0.352,-0.78 0.78,-0.78Zm1.44,6.78l-2.64,0c-0.263,0 -0.48,-0.217 -0.48,-0.48c0,-0.263 0.217,-0.48 0.48,-0.48l0.84,0l0,-2.64l-0.48,0c-0.263,0 -0.48,-0.217 -0.48,-0.48c0,-0.263 0.217,-0.48 0.48,-0.48l0.96,0c0.263,0 0.48,0.217 0.48,0.48l0,3.12l0.84,0c0.263,0 0.48,0.217 0.48,0.48c0,0.263 -0.217,0.48 -0.48,0.48Z">
                    </path>
                </svg>
                <svg v-if="item.type == 'warning'" class="noti_prompt-warning" xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 12 12" aria-hidden="true" fill="currentColor">
                    <path
                        d="M6,-0c-3.308,-0 -6,2.692 -6,6c-0,3.308 2.692,6 6,6c3.308,-0 6,-2.692 6,-6c-0,-3.308 -2.692,-6 -6,-6Zm-0,9.228c-0.316,0 -0.577,-0.26 -0.577,-0.577c0,-0.316 0.261,-0.577 0.577,-0.577c0.316,0 0.577,0.261 0.577,0.577c-0,0.317 -0.261,0.577 -0.577,0.577Zm0.627,-5.802l-0.166,3.519c-0,0.253 -0.208,0.462 -0.462,0.462c-0.253,-0 -0.461,-0.209 -0.461,-0.462l-0.166,-3.518l0,-0.001c-0,-0.009 -0,-0.018 -0,-0.027c-0,-0.344 0.283,-0.627 0.627,-0.627c0.344,0 0.627,0.283 0.627,0.627c-0,0.009 -0,0.018 -0.001,0.027l0.002,-0Z">
                    </path>
                </svg>
                <svg v-if="item.type == 'error'" class="noti_prompt-error" xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 12 12" aria-hidden="true">
                    <path
                        d="M6,-0c-3.308,-0 -6,2.692 -6,6c-0,3.308 2.692,6 6,6c3.308,-0 6,-2.692 6,-6c-0,-3.308 -2.692,-6 -6,-6Zm-0,9.228c-0.316,0 -0.577,-0.26 -0.577,-0.577c0,-0.316 0.261,-0.577 0.577,-0.577c0.316,0 0.577,0.261 0.577,0.577c-0,0.317 -0.261,0.577 -0.577,0.577Zm0.627,-5.802l-0.166,3.519c-0,0.253 -0.208,0.462 -0.462,0.462c-0.253,-0 -0.461,-0.209 -0.461,-0.462l-0.166,-3.518l0,-0.001c-0,-0.009 -0,-0.018 -0,-0.027c-0,-0.344 0.283,-0.627 0.627,-0.627c0.344,0 0.627,0.283 0.627,0.627c-0,0.009 -0,0.018 -0.001,0.027l0.002,-0Z">
                    </path>
                </svg>
                <svg v-if="item.type == 'promise'" class="noti_prompt-promise" xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 24 24" aria-hidden="true" width="28" height="28">
                    <path d="M12,1A11,11,0,1,0,23,12,11,11,0,0,0,12,1Zm0,19a8,8,0,1,1,8-8A8,8,0,0,1,12,20Z"
                        opacity=".25"></path>
                    <path
                        d="M10.14,1.16a11,11,0,0,0-9,8.92A1.59,1.59,0,0,0,2.46,12,1.52,1.52,0,0,0,4.11,10.7a8,8,0,0,1,6.66-6.61A1.42,1.42,0,0,0,12,2.69h0A1.57,1.57,0,0,0,10.14,1.16Z"
                        class="noti_prompt-spin"></path>
                </svg>
            </div>

            <div class="noti_prompt-text">
                <h5>{{ item.title }}</h5>
                <p>{{ item.message }}</p>
            </div>
        </div>





        <div class="noti_prompt-options">
            <button class="btn btn-prompt btn-sm"
                :class="'btn-' + (button.hasOwnProperty('style') ? button.style : 'primary')"
                v-for="(button, index) in item.props.buttons" @click="button.onclick(item);">
                <i :class="button.icon"></i> {{ button.label }}
            </button>
        </div>
    </div>


</template>


<script>

export default {

    props: {
        item: {
            type: Object,
            required: true
        }
    },
    mounted() {

        console.log(this.item);
    }

}

</script>

<style scoped>
.noti_prompt-dialog {
    width: 100%;
    min-width: 350px;
    height: 100%;
    padding: 20px;
    background: #fff;
    box-shadow: 0px 4px 10px rgba(100, 100, 100, .1);
    border-radius: 10px;


    .noti_prompt-content {
        display: flex;
        align-items: center;

        .noti_prompt-icon {
            margin-right: 10px
        }
    }

    .noti_prompt-options {
        text-align: right;
        margin-left: -5px;
        margin-right: -5px;

        button {
            margin: 0 5px
        }

    }


    .noti_prompt-icon {

        svg {
            width: 20px
        }

        .noti_prompt-success {
            fill: #28b780
        }

        .noti_prompt-info {
            fill: #3E8EFF
        }

        .noti_prompt-warning {
            fill: #F59E0B
        }

        .noti_prompt-error {
            fill: #E74C3C
        }

        .noti_prompt-promise {

            .noti_prompt-spin {
                animation: rotate .75s linear infinite !important;
                transform-origin: 12px;
            }
        }

    }
}


@keyframes rotate {

    from {
        transform: rotate(0deg)
    }

    to {
        transform: rotate(360deg)
    }


}
</style>
