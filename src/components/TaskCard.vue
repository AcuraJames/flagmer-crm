<template>
  <div class="task-card">
    <div class="task-card__header">
      <span class="task-card__name">{{ name }}</span>
      <span class="task-card__time">{{ time }}</span>
    </div>
    <div class="task-card__body">{{ text }}</div>
    <div class="task-card__footer">
      <div v-for="(tag, index) in tags" :key="index" class="tag">{{ tag }}</div>
      <div class="created-day">
        <span>{{ day }}</span>
        <div class="indicator"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TaskCard',
  props: {
    name: {
      type: String,
      default: 'Иван'
    },
    time: {
      type: [String, Date],
      default: '11:33'
    },
    text: {
      type: String,
      default:
        'Лид с формы "Оставить заявку на расчёт стоимости упаковки франшизы.'
    },
    tags: {
      type: Array,
      default: () => ['Холодный']
    },
    day: {
      type: String,
      default: 'Сегoдня'
    }
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/css/base.scss';
.task-card {
  @include card(5px);

  &__header,
  &__footer {
    @include card-flex;
  }

  &__header {
    color: $primary;
  }

  &__body {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  &__footer {
    margin-top: 3px;

    .tag {
      padding: 1px 3px;
      border: 1px solid #e9edf2;
      border-radius: 3px;
      color: $primary;
      font-size: 12px;
    }

    .created-day {
      display: flex;
      align-items: center;
      color: $success;

      .indicator {
        width: 4px;
        height: 4px;
        margin-left: 2px;
        border-radius: 20px;
        background-color: $success;
      }
    }
  }
}
</style>
