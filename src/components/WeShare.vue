<template>
  <a
  :href="baseurl()"
  :class="[
   'we-share-button',
   'we-share-button--' + mediatype,
   'we-share-button--' + size,
   {
    'we-share-button--rounded': rounded
   }
  ]" />
</template>

<script>
export default {
props: {
  mediatype: {
   type: String,
   validator(x) {
     return ["linkedin", "twitter", "facebook", "whatsapp", "telegram", "weibo"].indexOf(x) !== -1;
   }
  },
  rounded: {
   type: Boolean,
   default: true
  },
  size: {
   type: String,
   default: "default",
   validator(x) {
    return ["small", "default", "large"].indexOf(x) !== -1;
   }
  },
  link: {
    type:String
  },
  title: {
    type:String
  },
  body: {
    type:String
  },
  hashtags: {
    type:String
  }
 },
  methods: {
    baseurl() {
    if(this.mediatype==="linkedin") {
     return `https://www.linkedin.com/sharing/share-offsite/?url=${this.link}`
    }
    if(this.mediatype==="twitter") {
     return `https://twitter.com/intent/tweet?text=${this.body}&url=${this.link}&hashtags=${this.hashtags}`
    }
    if(this.mediatype==="facebook") {
     return `https://www.facebook.com/sharer/sharer.php?u=${this.link}&title=${this.title}&description=${this.body}`
    }
    if(this.mediatype==="whatsapp") {
     return `https://api.whatsapp.com/send?text=${this.body}`
    }
    if(this.mediatype==="telegram") {
     return `https://t.me/share/url?url=${this.link}&text=${this.body}`
    }
    if(this.mediatype==="weibo") {
     return `http://service.weibo.com/share/share.php?url=${this.link}&title=${this.title}`
    }
    }
  },
  }
</script>

<style>
.we-share-button {
 display: inline-block;
 outline: 0;
 border: 1px solid rgba(0, 0, 0, 0.1);
 color: #ffffff;
 font-weight: 500;
 font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
 user-select: none;
 cursor: pointer;
 background-size: 50%;
 background-repeat: no-repeat;
 background-position: center;
 margin-right:8px;
 width: 15px;
 height: 15px;
}

/* --> COLORS <-- */

.we-share-button--linkedin {
 background-color: #0077b5;
 background-image:url('./weshare/icons/linkedin.svg');
 background-size:60%;
}

.we-share-button--twitter {
 background-color: #1DA1F2;
 background-image:url('./weshare/icons/twitter.svg');
}

.we-share-button--facebook {
 background-color: #4267B2;
 background-image:url('./weshare/icons/facebook.svg');
}

.we-share-button--whatsapp {
 background-color: #25D366;
 background-image:url('./weshare/icons/whatsapp.svg');
}

.we-share-button--telegram {
 background-color: #229ED9;
 background-image:url('./weshare/icons/telegram.svg');
}

.we-share-button--weibo {
 background-color: #df2029;
 background-image:url('./weshare/icons/weibo.svg');
 background-size:60%;
}
/* --> SIZES <-- */

.we-share-button--small {
 padding: 10px 10px;
 border-radius: 4px;
}

.we-share-button--default {
 padding: 14px 14px;
 border-radius: 6px;
}

.we-share-button--large {
 padding: 18px 18px;
 border-radius: 8px;
} 

/* --> BOOLEANS <-- */

.we-share-button--rounded {
 border-radius: 100%;
}
</style>