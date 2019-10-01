<template lang="pug">
  .insta-header
    .insta-profile-picture: img(:src="avatar")
    .insta-handle {{handle}}
    .insta-status {{status}}
</template>

<script>
export default {
  props: [
    'avatar',
    'handle',
    'status'
  ]
}
</script>

<style lang="scss" scoped>
.insta-header {
  display: grid;
  grid-template-columns: 64px auto;
  grid-template-rows: 1fr 1fr;
  text-align: left;
  grid-gap: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  font-size: 14px;
  color: #262626;
  border-bottom: 1px solid #efefef;
  @media(-webkit-min-device-pixel-ratio: 2) {
    border-bottom-width: .5px;
  }
}
.insta-profile-picture {
  grid-column: 1/2;
  grid-row: 1/3;
  padding: 14px 16px 13px;
  > img {
    width: 32px;
    height: 32px;
    border-radius: 16px;
  }
}
.insta-handle {
  grid-column: 2/3;
  grid-row: 1/2;
  font-weight: 600;
  align-self: end;
  line-height:18px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding-right: 19px;
}
.insta-status {
  grid-column: 2/3;
  grid-row: 2/3;
  line-height: 15px;
  font-size: 12px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding-right: 19px;
}
</style>
