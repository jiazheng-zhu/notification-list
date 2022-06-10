<template>
    <div calss="notification info" :class="{
    info: notifDetails.type== 'info',
    warning:notifDetails.type=='warning',
    urgent:notifDetails.type== 'urgent',
    readStatus: notifiDetails.read_status == true,}">
        <p>{{ notifDetails.description }}</p> 
        <p>{{ TimeSet(notifiDetails.timestamp) }}</p>
    </div>
</template>

<script>
import timeMoment from "timeMoment";
export default {
  name: "SingleNotification",
  props: {
    notifiDetails: Object,
  },
  methods: {
    TimeSet: function (value) {
      return timeMoment.unix(value).format("DD/MM - hh:mm");
    },
  },
};
</script>

<style lang="scss">
    .notification{
        padding:5px;
        box-sizing:border-box;
}
    .info {
        border-left:3px solid lightskyblue;
    }
    .warning {
        border-left:3px solid orange;
    }
    .urgent {
        border-left:3px solid red;
    }
    
</style>




