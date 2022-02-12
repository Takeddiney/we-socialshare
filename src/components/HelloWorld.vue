<template>
  <button :class="[
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
}

/* --> COLORS <-- */

.we-share-button--linkedin {
 background-color: #0077b5;
}

.we-share-button--twitter {
 background-color: #1DA1F2;
}

.we-share-button--facebook {
 background-color: #4267B2;
}

/* --> SIZES <-- */

.we-share-button--small {
 padding: 10px 10px;
 border-radius: 4px;
 font-size: 12px;
 line-height: 12px;
}

.we-share-button--default {
 padding: 14px 14px;
 border-radius: 6px;
 font-size: 14px;
 line-height: 16px;
}

.we-share-button--large {
 padding: 18px 18px;
 border-radius: 8px;
 font-size: 16px;
 line-height: 20px;
} 

/* --> BOOLEANS <-- */

.we-share-button--rounded {
 border-radius: 20px;
}
</style>