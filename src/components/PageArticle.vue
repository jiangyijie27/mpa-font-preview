<template>
    <article :style="{fontFamily: font + ', -apple-system, BlinkMacSystemFont, PingFang SC, Microsoft YaHei' }" @click="fontClose()">
        <div class="font">
            <div class="font__primary" :class="{'font__primary_open' : fontOpen}" @click.self.stop="toggleOpen($event)">
                {{ font }}

                <div class="font__list-wrapper">
                    <ol class="font__list">
                        <li v-for="font in fontList" @click.stop="toggleOpen($event)">
                            {{ font.family }}
                        </li>
                    </ol>
                </div>
            </div>
        </div>
        <section class="section__part1">
            <h2>1234567890</h2>
            <h3>1234567890</h3>
            <p>1234567890</p>
            <p>1234567890</p>
            <p>1234567890</p>
            <i class="section__divider" style="margin: 30px 0 20px 2px;"></i>
            <section class="section__part2">
                <h2>38%</h2>
                <h3>4,642.8</h3>
                <div>395572.50</div>
                <div>
                    <span>92.59%</span>
                    <span>2016-3-24</span>
                    <span>396651.09</span>
                    <span>14:09</span>
                </div>
            </section>
        </section>
        <section class="section__table">
            <div class="section__table-row">
                <span>1,4742.112</span>
                <span>1,0068.900</span>
                <span>1,0069.900</span>
                <span>1,0068.943</span>
                <span>1,4742.112</span>
            </div>
            <div class="section__table-row">
                <span>1,4743.909</span>
                <span>1,0689.588</span>
                <span>1,0686.588</span>
                <span>1,0420.564</span>
                <span>1,4743.909</span>
            </div>
        </section>
        <i class="section__divider" style="margin: 16px 0 30px 2px;"></i>
        <p class="section__para0">
            用户主动转发广告 4,928 次（转发好友 928 次，转发朋友圈 1,928 次），使得品牌在好友对话框和朋友圈再次传播，为品牌带来 492,812 次额外曝光。
        </p>
        <p class="section__para1">
            乐队的一首经典老歌《 1030 现在的你在哪里》，青春洋溢的歌声不仅让如今的年轻人纷纷询问，曝光最近 5,000 万次。
        </p>
        <footer>
            A type tool by TAD
        </footer>
    </article>
</template>

<script>
import Vue from 'vue';
import vueTap from '../lib/vue-tap';
Vue.use(vueTap);

export default {
  props: {
      fontOpen: {
        type: Boolean,
        default: false
      },
  },
  data() {
    return {
        font : "Work Sans",
        fontList : [
            {
                family : "Arial"
            },
            {
                family : "Avenir Next"
            },
            {
                family : "Helvetica"
            },
            {
                family : "Helvetica Neue"
            },
            {
                family : "Microsoft YaHei"
            },
            {
                family : "Open Sans"
            },
            {
                family : "PingFang SC"
            },
            {
                family : "Roboto"
            },
            {
                family : "Segoe UI"
            },
            {
                family : "SF UI"
            },
            {
                family : "Ubuntu"
            },
            {
                family : "Work Sans"
            }
        ]
    }
  },
  methods:{
      fontClose(){
          this.fontOpen = false;
      },
      toggleOpen(event){
          if(event.target.tagName.toLowerCase() === "li" ){
              this.font = event.target.innerHTML
              this.$nextTick(function(){
                  const article = document.querySelector("article");
                  console.log(window.getComputedStyle(article,null).getPropertyValue("font-family"));
              })
          }
          this.fontOpen = !this.fontOpen
      }
  }
};
</script>
<style lang="less">
article{
    position: relative;
    max-width: 650px;
    margin: 0 auto;
    color: #313131;
}
.section__part1{
    position: relative;
    margin-bottom: 37px;

    h2{
        margin-bottom: 5px;
        letter-spacing: 1px;
        font-size: 56px;
        font-weight: 700;
        line-height: 66px;
    }
    h3{
        margin-bottom: 9px;
        font-size: 42px;
        font-weight: 500;
        line-height: 49px;
    }
    p{
        &:first-of-type{
            margin-bottom: 15px;
            font-size: 24px;
            font-weight: 400;
            line-height: 28px;
        }
        &:nth-of-type(2){
            margin-bottom: 18px;
            font-size: 16px;
            font-weight: 400;
            line-height: 19px;
        }
        &:last-of-type{
            font-size: 12px;
            font-weight: 400;
            line-height: 14px;
        }
    }
}
.section__part2{
    position: absolute;
    bottom: 0;
    right: 0;
    text-align: right;

    h2{
        margin-bottom: 6px;
        font-size: 40px;
        font-weight: 700;
        line-height: 47px;
    }
    h3{
        margin-bottom: 11px;
        font-size: 40px;
        font-weight: 700;
        line-height: 47px;
    }
    div{
        &:first-of-type{
            margin-bottom: 19px;
            font-size: 24px;
            font-weight: 500;
            line-height: 28px;
        }
        &:last-of-type{
            font-size: 14px;
            font-weight: 400;
            line-height: 16px;
        }
    }
}
.section__table{
    margin-bottom: 33px;
    font-size: 12px;
    font-weight: 400;
    line-height: 24px;
    text-align: right;
    border: 1px solid currentColor;
}
.section__table-row{
    display: flex;
    flex-direction: row;
    box-sizing: border-box;
    border-bottom: 1px solid currentColor;

    &:last-of-type{
        border-bottom: none;
    }

    span{
        flex: 1;
        box-sizing: border-box;
        padding-right: 6px;
        border-right: 1px solid currentColor;

        &:last-of-type{
            border-right:none;
        }
    }
}
.section__para0{
    margin-bottom: 20px;
    font-size: 14px;
    line-height: 24px;
}
.section__para1{
    margin-bottom: 52px;
    font-size: 10px;
    line-height: 14px;
}
footer{
    position: relative;
    max-width: 650px;
    margin: 0 auto 30px;
    padding-top: 10px;
    font-size: 10px;
    line-height: 14px;
    color: #ccc;

    &::before{
        content: "";
        position: absolute;
        left: 0;
        top: 0;
        width: 12px;
        height: 1px;
        background: #eee;
    }
}
.font{
    position: relative;
    color: #434343;
    font-family: "Open Sans";
    font-size: 12px;
    line-height: 34px;
}
.font__primary{
    position: relative;
    box-sizing: border-box;
    margin-bottom: 41px;
    padding-left: 12px;
    width: 205px;
    height: 34px;
    border: 1px solid #ccc;
    border-radius: 2px;
    cursor: pointer;
    transition: .2s border-color all;
    -webkit-tap-highlight-color: rgba(0,0,0,0);
    -webkit-user-select: none;
    user-select: none;

    &:hover{
        border-color: #a6a6a6;
    }

    &::after{
        content: "";
        position: absolute;
        top: 50%;
        right: 12px;
        width: 5px;
        height: 5px;
        border-right: 1px solid #A6A6A6;
        border-bottom: 1px solid #A6A6A6;
        transform: translate(0,-50%) rotate(45deg);
    }
}
.font__list{
    position: absolute;
    display: none;
    box-sizing: border-box;
    z-index: 1;
    top: 100%;
    left: -1px;
    width: 205px;
    height: 172px;
    background: #fff;
    list-style: none;
    border: 1px solid #a6a6a6;
    border-top-color: #ccc;
    border-bottom-left-radius: 2px;
    border-bottom-right-radius: 2px;
    overflow-x: hidden;
    overflow-y: scroll;
    cursor: pointer;
    transition: .2s ease all;
    -webkit-overflow-scrolling: touch;

    &::-webkit-scrollbar-track{
    	border-radius: 10px;
    }
    &::-webkit-scrollbar{
        margin-right: 5px;
    	width: 5px;
    	background-color: rbga(0,0,0,0);
    }
    &::-webkit-scrollbar-thumb{
    	border-radius: 10px;
    	background-color: #7b7b7b;
    }

    li{
        padding-left: 12px;
        transition: .2s ease all;

        &:hover{
            background: #f2f2f2;
        }
    }
}
.font__primary_open{
    border-color: #a6a6a6;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;

    .font__list{
        display: block;
    }
}
.section__divider{
    display: none;
    width: 12px;
    height: 1px;
    background: #313131;
    transform: scaleY(.5);
}
</style>
