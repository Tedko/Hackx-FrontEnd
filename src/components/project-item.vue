<template>
  <p class="note" v-text="note"></p>
  <div class="panel hackx">
    <div class="panel-image hackx">
      <place-holder
        width="130"
        height="130"
        text="SUPER AWESOME PROJECT PICTURE"
      >
      </place-holder>
    </div>
    <div class="panel-content hackx">
      <div class="panel-title hackx">
        {{title}}
      </div>
      <div class="panel-subtitle hackx">
        {{subtitle}}
      </div>
      <div class="panel-content-body hackx">
        <label-item
          v-for="t in tags"
          :icon="t.icon"
          :title="t.title">
        </label-item>
      </div>
      <div class="panel-content-body hackx">
        <span class="panel-text hackx">
          {{desc}}
        </span>
      </div>
    </div>
    <div class="panel-action hackx">
      <action-button title="DEMO"></action-button>
    </div>
  </div>
</template>

<style lang="sass" scoped>
@import "../styles/defaults.scss"

.note
  font-size: zoom(10px)
  color: $text-color

.panel.hackx
  display: flex
  flex-direction: row
  @include sm-only
    flex-direction: column
  flex-wrap: nowrap
  justify-content: space-between

  overflow: hidden
  background: $panel-background-color
  border: solid .5px $panel-border-color
  border-radius: 0px

  padding: zoom(10px) zoom(9.5px)

.panel-image.hackx
  flex-shrink: 0

  height: zoom(70px)
  width: zoom(70px)
  @include sm-only
    width: 100%
    height: auto
  user-select: none

.panel-content
  display: flex
  flex-direction: column
  font-size: 0

  margin-left: zoom(10px)
  flex-grow: 1

.panel-title
  @include title(12px)

.panel-subtitle
  @include subtitle(10px)

.panel-content-body
  margin-top: 2px
  .panel-text
    font-size: zoom(7px)
    color: $panel-text-color
    line-height: 1.4em

.panel-action
  align-self: center
  flex-shrink: 0
  margin-left: zoom(10px)

  width: percentage(115/430)

</style>

<script>
import PlaceHolder from "./placeholder.vue"
import LabelItem from "./label.vue"
import ActionButton from "./action-btn.vue"

export default {
  components : {
    PlaceHolder, LabelItem, ActionButton
  },
  props : ['note', 'title', 'subtitle', 'desc', 'tags', 'image', 'action']
}
</script>