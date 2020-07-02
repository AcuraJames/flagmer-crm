<template>
  <div class="home">
    <Header @showModal="modal = !modal" />
    <main>
      <transition name="slide">
        <Modal v-if="modal" />
      </transition>
      <div class="stat-card-container">
        <StatCard
          v-for="stat in stats"
          :key="stat.id"
          :name="stat.name"
          :diff="stat.diff"
          :stat="stat.stat"
          :short="stat.stat.length <= 4"
          :success="stat.diffValue === 'positive'"
          :loss="stat.diffValue === 'negative'"
        />
        <StatCard>
          <template v-slot:header>
            <span class="more-stat">Больше статистики</span>
            <img src="@/assets/icons/arrow.svg" />
          </template>
        </StatCard>
      </div>
      <div class="stage-container">
        <Stage
          v-for="(item, index) in 5"
          :key="index"
          :title="titles[index]"
          :num="nums[index]"
          :count="count[index]"
        />
      </div>
    </main>
  </div>
</template>

<script>
import Header from '@/components/Header'
import StatCard from '@/components/StatCard'
import Stage from '@/components/Stage'
import Modal from '@/components/Modal'
export default {
  name: 'Home',
  components: {
    Header,
    StatCard,
    Stage,
    Modal
  },
  data() {
    return {
      modal: false,
      stats: [
        {
          id: 1,
          name: 'Прибыль (руб.)',
          diff: '+47%',
          diffValue: 'positive', //
          stat: '1,240,650'
        },
        { id: 2, name: 'Ожидается (руб.)', diff: '(382)', stat: '2,200,340' },
        {
          id: 3,
          name: 'Рост',
          diff: '-27%',
          diffValue: 'negative',
          stat: '104%'
        },
        { id: 4, name: 'Возврат', diff: '(14)', stat: '- 287,000' },
        { id: 5, name: 'Клиенты', diff: '', stat: '367' },
        {
          id: 6,
          name: 'LTV (руб.)',
          diff: '-27%',
          diffValue: 'positive',
          stat: '1,200'
        }
      ],
      titles: [
        'Новые',
        'Квалификация',
        'Перезвонить',
        'Остались возражения',
        'Оплатили'
      ],
      nums: ['7', '1', '2', '1', '1'],
      count: [15, 3, 4, 12, 3]
    }
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/css/base.scss';
.home {
  background-color: #f3f6f8;

  main {
    height: calc(100vh - 50px);
    padding: 0 80px;
    overflow-x: auto;
    position: relative;

    @media (max-width: 992px) {
      padding: 0 30px;
    }
  }
}
.stat-card-container {
  display: flex;
  overflow-x: auto;

  .more-stat {
    color: $accent;
    border-bottom: 1px solid rgba(57, 139, 255, 0.15);
    font-size: 12px;
  }
}
.stage-container {
  height: calc(100% - 155px);
  display: flex;
}

.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s ease;
}
.slide-enter,
.slide-leave-to {
  transform: translateX(100%);
}
</style>
