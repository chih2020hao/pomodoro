<template lang="pug">
  #settings
    b-container
      b-row
        b-col(cols="12")
          b-table(:items="items" :fields="fields" @row-clicked="selectAlarm")
            template(#cell(file)="data")
              audio(controls :src="'./sounds/'+data.item.file")
            template(#cell(select)="data")
              font-awesome-icon(v-if="data.item.file === alarm" :icon="['fas', 'check']")
</template>

<script>
export default {
  name: 'Settings',
  data () {
    return {
      items: [
        {
          name: '鬧鈴',
          file: 'alarm1.mp3'
        },
        {
          name: '土撥鼠',
          file: 'ahhhhhhhh.mp3'
        },
        {
          name: '呷土豆',
          file: 'jatoudoau.mp3'
        },
        {
          name: '江西南',
          file: 'johncena.mp3'
        },
        {
          name: 'dejavu',
          file: 'dejavu2018.mp3'
        },
        {
          name: '好~~~',
          file: 'hao.mp3'
        },
        {
          name: '歐郎',
          file: 'niggaeatfruit.mp3'
        }
      ],
      fields: [
        {
          key: 'name',
          label: '名稱'
        },
        {
          key: 'file',
          label: '預覽'
        },
        {
          key: 'select',
          label: '選擇'
        }
      ]
    }
  },
  computed: {
    alarm () {
      return this.$store.state.alarm
    }
  },
  methods: {
    selectAlarm (item) {
      this.$store.commit('selectAlarm', item.file)
    }
  }
}
</script>
