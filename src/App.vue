<script setup lang="ts">
import MyLink from './components/myLink.vue';

interface NavGroup {
  key: string,
  name: string,
  items: Array<{
    text: string,
    link: string,
    info?: string,
  }>,
}

const navList: NavGroup[] = [
  {
    key: 'my-app-h5',
    name: '自制应用-H5平台',
    items: [
      { text: '我的博客', link: 'https://kljzndx.github.io/blog/' },
      { text: '彩票号码生成器', link: 'https://kljzndx.github.io/lottery-number-builder/' },
      { text: '按键手机仿真器', link: 'https://kljzndx.github.io/key-phone/' },
      { text: '贪吃蛇游戏', link: 'https://kljzndx.github.io/snake-game/' },
      { text: '打字练习', link: 'https://kljzndx.github.io/da-zi-lian-xi/' },
      { text: '四则运算表格', link: 'https://kljzndx.github.io/math-table/' },
    ],
  },
  {
    key: 'my-app-uwp',
    name: '自制应用-UWP平台',
    items: [
      { text: '歌词(lrc字幕)编辑器', link: 'https://www.microsoft.com/store/apps/9MX4FRGQ4RQS' },
      { text: '歌词(lrc字幕)制作器', link: 'https://www.microsoft.com/store/apps/9NWDP77WF36W' },
      { text: '歌曲播放器', link: 'https://www.microsoft.com/store/apps/9N6406PNNRZS' },
      { text: '有声书播放器', link: 'https://www.microsoft.com/store/apps/9MXKGW577LN7' },
    ],
  },
  {
    key: 'dev-tools',
    name: '开发工具',
    items: [
      { text: 'git', link: 'https://git-scm.com/' },
      { text: 'git gui', link: 'https://tortoisegit.org/' },
      { text: 'notepad-- (NPP 平替)', link: 'https://gitee.com/cxasm/notepad--/releases' },
      { text: 'visual studio', link: 'https://visualstudio.microsoft.com/' },
      { text: 'jetbrains', link: 'https://www.jetbrains.com/' },
      { text: 'android studio', link: 'https://developer.android.google.cn/studio' },
    ],
  },
  {
    key: 'mini-tools-win10',
    name: '实用小工具-win10平台',
    items: [
      { text: 'everything', info: '超速文件搜索器', link: 'https://www.voidtools.com/' },
      { text: 'space-sniffer', info: '磁盘空间嗅探器', link: 'https://sourceforge.net/projects/spacesniffer/' },
      { text: 'hwinfo', info: '硬件信息查看器', link: 'https://www.hwinfo.com/' },
      { text: 'watt toolkit', info: 'steam, github 访问加速器', link: 'https://steampp.net/' },
      { text: 'DiskGenius', info: '专业分区软件', link: 'https://www.diskgenius.cn/' },
    ],
  },
]

</script>

<template>
  <div class="main">
    <ul>
      <li class="group-li" v-for="group of navList">
        <h3 class="gp-title">{{ group.name }}</h3>
        <div class="separator"></div>
        <ul class="link-ul">
          <li v-for="item of group.items">
            <MyLink :text="item.text" :info="item.info" :link="item.link"></MyLink>
          </li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.main {
  max-width: 60rem;
  margin: 0 auto;
  padding: 0 1rem;
}

.group-li {
  margin: 0.5rem 0;
  background-color: hsl(0, 0%, 90%);
  border: 0.5rem solid hsl(0, 0%, 90%);
}

.gp-title {
  margin: 0;
}

.separator {
  height: 0.25rem;
  background-color: hsl(0, 0%, 70%);
  margin-top: 0.25rem;
}

.link-ul {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  padding: 0.5rem;
  padding-top: 1rem;
  background-color: white;
}
</style>
