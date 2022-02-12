<template>
  <a
  :href="shareurl"
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
   default: "linkedin",
   validator(x) {
     return ["linkedin", "twitter", "facebook"].indexOf(x) !== -1;
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
  shareurl: {
    type:String,
    default:"#"
  }
 }
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
 border-radius: 20px;
}
</style>