<template>
  <div class="select">
    <input type="text" class="select__input">
    <vue-perfect-scrollbar class="select__drop">
      <div>
        <a href="#" class="select__drop-link">Value text</a>
        <i class="icon-confirm select__check"></i>
      </div>
    </vue-perfect-scrollbar>
  </div>
</template>

<script>
import VuePerfectScrollbar from 'vue-perfect-scrollbar'
export default {
  name: 'Select',
  components: {
    VuePerfectScrollbar
  },
  data: function () {
    return {

    }
  }
}
</script>

<style lang="scss">
  .select {
    position: relative;
    height: 40px;
    background: #ffffff;
    cursor: pointer;
    font-size: 14px;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    color: #262929;
    flex-grow: 1;
    border-radius: 3px;
    transition: background-color .2s ease-in;
    user-select: none;

    &_lg-height {
      height: 50px;
    }

    &_small {
      height: 32px;
    }

    &_disabled {
      cursor: default;
      background-color: #eeeeee;

      .select__input {
        cursor: default;
        border: 1px solid #e1e1e1 !important;
      }

      &:before{
        border-color: rgba(0,0,0, 0.3) transparent transparent transparent !important;
      }
    }

    &_widget-ticket {
      height: calc(100% - 2px);
      margin: 1px;
      border: none;

      .select__input {
        border: none !important;
        border-radius: 0;
      }
    }

    &_filter {
      .select__drop {
        max-height: none;
      }
    }

    &:before {
      content: '';
      position: absolute;
      z-index: 0;
      right: 15px;
      top: 50%;
      transform: translateY(-50%);
      margin-top: 2px;
      border: 4px solid;
      border-color: #9da0a2 transparent transparent transparent;
      transition: border-color .3s;
    }

    &:hover, &_open {
      &:before{
        z-index: 6;
      }
    }

    &_checked {
      .select__input{
        border-color: #02C8F3;
      }
    }

    &:hover{
      &:before{
        border-color: #02C8F3 transparent transparent transparent;
      }

      .select__input {
        border-color: #02C8F3;
      }
    }

    &_open {
      background: #ffffff;
      z-index: 5;

      .select__input{
        border-color: #e1e1e1 !important;
      }

      &:before{
        border-color: #02C8F3 transparent transparent transparent !important;
      }

      .select__drop {
        display: block;
      }
    }

    &__input {
      width: 100%;
      height: 100%;
      border: 1px solid #e1e1e1;
      border-radius: 3px;
      background-color: transparent;
      padding: 0 2rem 0 1rem;
      cursor: pointer;
      font-family: inherit;
      font-size: inherit;
      transition: border-color .2s ease-in;
      user-select: none;
      box-sizing: border-box;
      outline: none;
    }

    &__drop {
      display: none;
      position: absolute!important;
      top: 100%;
      left: 0;
      z-index: 5;
      width: 100%;
      max-height: 195px;
      margin-top: 2px;
      overflow: hidden;
      border-radius: 3px;
      padding: 4px 0;
      border: 1px solid #e5e5e5;
      background: #ffffff;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
      color: #262929;

      &_top {
        bottom: 100%;
        margin-bottom: 2px;
        top: auto;
      }

      &_bottom {
        bottom: 0;
        top: auto;
      }

      &-link {
        display: block;
        padding: 9px 37px 8px 11px;
        text-decoration: none;
        color: #262929 !important;
        transition: color 200ms ease-in;

        &_checked {
          position: relative;
          background-color: transparent;
          color: #02C8F3 !important;
        }
      }

      > div {
        position: relative;

        &:hover {
          a {
            background: #f1f1f1;
          }
        }
      }
    }

    &__check {
      position: absolute;
      display: none;
      top: 50%;
      right: 16px;
      transform: translateY(-50%);
      font-size: 10px;
      color: #02C8F3;

      &_checked {
        display: block;
      }
    }
  }

  .select-row {
  display: flex;

    .select + .select {
      margin-left: 10px;
    }

    .select + .text-field {
      margin-left: 10px;
    }
  }
</style>
