<template>
	<div class="loader" v-show="loadingOptions && loadingOptions.loading">
		<div class="cui-grayload-squre">
			<div class="g-m-c"></div>
			<div class="g-m-l"></div>
			<div class="cui-grayload-bfont">
				正在加载...
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {};
		},
		props: {
			loadingOptions: {
				default: {
					loading: false
				}
			}
		}
	};
</script>

<style lang="less" scoped>
@white: #fff;
.rotating(@rotate: 45deg) {
    transform: rotate(@rotate);
}

@keyframes locate-loading{
    0%{
        opacity: 1;
        .rotating(0deg);
    }
    100%{
        opacity: 1;
        .rotating(360deg);
    }
}

.loader{
    position: fixed;
    left:0px;
    top:0px;
    width: 100%;
    height: 100%;
    z-index: 9999;
    background: rgba(0, 0, 0, 0.5);
    .cui-grayload-squre{
        position: absolute;
        width: 5rem;
        height: 5rem;
        left: 50%;
        top: 50%;
        transform: translate3d(-50%,-50%,0);
        font-size: .8rem;
        text-align: center;
        background: rgba(0, 0, 0, 0.7);
        color: @white;
        border-radius: .25rem;
        z-index: 99;
        .g-m-c{
            position: absolute;
            left: 50%;
            top: 40%;
            width: 2.4rem;
            height: 2.4rem;
            margin: -1.25rem 0 0 -1.25rem;
        }
        .g-m-l{
            position: absolute;
            left: 50%;
            top: 40%;
            width: 1.4rem;
            height: 1.4rem;
            margin: -.7rem 0 0 -.7rem;
        }
        .g-m-c{
            animation-name: locate-loading;
            animation-duration: 1.58s;
            animation-timing-function: linear;
            animation-iteration-count: infinite;
            border-top: 2px solid @white;
            border-left: 2px solid @white;
            border-radius: 50%;
        }
        .g-m-l{
            background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAA2CAMAAAC2heqoAAAAhFBMVEUAAAD///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////8g2+bRAAAAK3RSTlMA8U0C+bkL/CZ+9cs4Fgftw5N3cT8Qpp1ZRizn3tlsXx+MUzKwl2Yc4tGGuUvfggAAAo1JREFUSMeVltfWqjAQhUPvAgpIR4qNef/3OyFRYgzB838XLlnuJFP2EJEUzXeM2gW9Mk4B+s19rmBFj80f8svZAo7mvic/OC5842lyffmEDW5S/U3nhFFswMJTFs6Zk1vDKbYTEmG6qTcN4LjGlR8jBzDF/YAYdufE8y0JIuBRlWs6IP+defLa9tiAhPwRYUGyNoS0sKhAitHB1AUsrwHrcwt2iJM2cdijj9Cowy7uU2EPGT7AgN94dFPFWdqtW1ObE+vIqTr1dGwL6sCBJH6EfZoC8SR7aiXLBXs7UrU1qYcNR4TSRmwPQgsyVLSJ98cFF5Aybi44yQu0PZmG0FrHY17YQOHlequhkn6z/yeFMFkminzt0CYFb89x7eQRbdOJhfR1fNLAJDtFOiNMGkI9B5yIuYm3qkLfJoHJq2MX6kI4QR52RkpWru+6j4qSA5Ivvf2OVqzSROLpEY9KfB7bbAP+levkiGdckvPN3OloahrrNAnzWSKeFADyS4M/6/uXlw7kZ2HEXOzCiZmLlcklTXORuCA6WLTsq5nYo6oIdwDAlAIFEaL3xJMFQkglwPnOFJgBXlzIglL0Tu9TQYUIWvPhvBFObyX7tXjl6bHWEPolYt0Q3NxoERN8VvahkYxGzhgKPtkHyurAu8JiuoHxqX8AXLVo3fDNwGJMFWjXirYKQKbNG2Z2mJuOYHV468uo9hVA2K4T8+DG5EqbbeNtnwCxWfbRo/auuRlksGbAEcNCHdA8w7mkXZtXbzrCO5n4pcHdo5d/6BlR+HHLI4GkJjoVO7AWLorN6TV7nZjYRunXvff0pf+tyJIpT+0zG6xo0JCU4OTRi9DIKmq464h+EOS9UYck7ezoc5v/A8imzeBKssPpAAAAAElFTkSuQmCC) no-repeat;
            background-size: 1.2rem 1.35rem;
            z-index: 9;
        }
        .cui-grayload-bfont{
            margin: 2.0rem 0 .3rem;
            font-size: .7rem;
        }
    }
    
}
</style>

