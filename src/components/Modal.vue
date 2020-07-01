<template>
  <div class="modal">
    <div class="modal__header">
      <div class="service-info">
        <div>#486542</div>
        <div>Сегодня в 11:33</div>
      </div>
      <div class="title">
        "Лид с формы "Оставить заявку на расёт стоимости упаковки франшизы"
      </div>
      <div class="contacts-title">Контакты</div>
      <div class="contacts">
        <ul>
          <li>
            <span>Имя</span>
            <span>Константинов Константин</span>
          </li>
          <li>
            <span>Телефон</span>
            <span>79101340155</span>
          </li>
          <li>
            <span>Email</span>
            <span>long-long-johnson@meow.com</span>
          </li>
        </ul>
      </div>
    </div>
    <div class="modal__body">
      <div class="history">
        <div class="history__header">
          <div class="history__icon"></div>
          <span class="history__title">История</span>
          <span class="history__number">6</span>
        </div>
        <div class="history__body">
          <div class="history__card">
            <input
              type="text"
              placeholder="Напишите текст Заметки или Сообщения..."
            />
            <div class="history-card__footer">
              <span class="history-card-action">Отменить</span>
              <span class="history-card-action">Отправить</span>
            </div>
          </div>
          <div v-for="(item, index) in 9" :key="index" class="history__card">
            <div class="history-card__header">
              <span class="name">Максим Солдаткин</span>
              <span class="time">1д</span>
            </div>
            <div class="history-card__body">Отправить КП по заявке 🔥</div>
            <div class="history-card__footer">
              <span class="date">10 мая в 11:33</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal'
}
</script>

<style scoped lang="scss">
@import '@/assets/css/base.scss';
.modal {
  max-width: 420px;
  height: 100%;
  overflow-y: auto;
  position: fixed;
  top: 50px;
  right: 0;
  background-color: #f3f6f8;
  -webkit-box-shadow: -3px 0px 15px -2px rgba(102, 101, 102, 1);
  -moz-box-shadow: -3px 0px 15px -2px rgba(102, 101, 102, 1);
  box-shadow: -3px 0px 15px -2px rgba(102, 101, 102, 1);

  @include scroll;

  &__header {
    height: auto;
    padding: 10px 20px 35px;
    background-color: #fff;

    .service-info {
      display: flex;
      justify-content: space-between;
      color: $primary;
      font-size: 12px;
    }
    .title {
      margin-top: 4px;
      text-align: left;
      color: #35383d;
      font-size: 18px;
    }

    .contacts-title {
      margin-top: 8px;
      padding-bottom: 8px;
      text-align: left;
      border-bottom: 1px solid #e9edf2;
      color: $primary;
    }
    .contacts ul {
      margin: 0;
      padding: 0;
      list-style: none;

      li {
        display: flex;
        margin-top: 8px;
        text-align: left;

        span:first-child {
          width: 30%;
          color: $primary;
        }
        span:latst-child {
          width: 70%;
          color: #35383d;
        }
      }
    }
  }

  &__body {
    margin-bottom: 60px;

    .history {
      @include stage(380px, margin, auto);
    }
    .history__header {
      @include stage-header;

      .history__icon {
        @include stage-header-icon($success);
      }

      .history__number {
        margin-left: auto;
      }
    }

    .history__card {
      @include card(10px);
      margin-bottom: 12px;

      input {
        width: 100%;
        height: 100%;
        padding-bottom: 10px;
        border: none;

        &::placeholder {
          color: $primary;
        }
        &:focus {
          outline: none;
        }
      }

      .history-card__header,
      .history-card__footer {
        @include card-flex;

        .name {
          color: #35383d;
        }
        .time {
          color: $primary;
        }
      }
      .history-card__body {
        margin-top: 5px;
        margin-bottom: 10px;
        text-align: left;
        font-size: 14px;
      }
      .history-card__footer {
        padding-top: 10px;
        border-top: 1px solid #e9edf2;
        color: $primary;

        .history-card-action {
          cursor: pointer;
        }
      }
    }
  }
}
</style>
