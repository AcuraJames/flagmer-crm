<template>
  <div class="stage">
    <div class="stage__header">
      <div class="stage__icon"></div>
      <span class="stage__title">{{ title }}</span>
      <span class="stage__number">{{ num }}</span>
    </div>
    <div class="stage-wrapper">
      <div class="stage__body">
        <TaskCard v-for="(item, index) in count" :key="index" />
      </div>
    </div>
  </div>
</template>

<script>
import TaskCard from '@/components/TaskCard'
export default {
  name: 'Stage',
  components: { TaskCard },
  props: {
    title: {
      type: String,
      default: 'New'
    },
    num: {
      type: String,
      default: '1'
    },
    count: {
      type: Number,
      default: 1
    }
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/css/base.scss';
.stage {
  @include stage(280px, margin-right, 20px);

  .stage__header {
    @include stage-header;

    .stage__icon {
      @include stage-header-icon(#d2d8de);
    }

    .stage__number {
      margin-left: auto;
    }
  }

  .stage-wrapper {
    width: 286px;
    height: 100%;
    overflow-y: auto;
    overflow-x: hidden;

    @include scroll;
  }
}
</style>
