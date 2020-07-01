<template>
  <div :class="['stat-card', { 'stat-card--short': short }]">
    <div class="stat-card__header">
      <slot name="header">
        <span class="name">{{ name }}</span>
        <span
          :class="[
            'diff',
            { 'diff--success': success },
            { 'diff--loss': loss }
          ]"
          >{{ diff }}</span
        >
      </slot>
    </div>
    <div class="stat-card__body">
      <span :class="['stat', { 'stat--loss': loss }]">{{ stat }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StatCard',
  props: {
    name: {
      type: String,
      default: ''
    },
    diff: {
      type: String,
      default: ''
    },
    stat: {
      type: String,
      default: ''
    },
    short: {
      type: Boolean,
      default: false
    },
    success: {
      type: Boolean,
      default: false
    },
    loss: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/css/base.scss';
.stat-card {
  width: 180px;
  min-width: 145px;
  height: 65px;
  margin: 20px 10px 20px 0;
  padding: 7px;
  border-radius: 5px;
  background-color: #fff;
  box-sizing: border-box;
  cursor: pointer;
}
.stat-card--short {
  width: 80px;
  min-width: 80px;
}
.stat-card__header {
  display: flex;
  justify-content: space-between;

  .name,
  .diff {
    color: $primary;
    font-size: 12px;
  }

  .diff--success {
    color: $success;
  }
  .diff--loss {
    color: $loss;
  }
}
.stat-card__body {
  float: right;
  margin-top: 7px;
  font-size: 24px;

  .stat--loss {
    color: $loss;
  }
}
</style>
