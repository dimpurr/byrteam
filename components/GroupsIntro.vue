<template>
    <section class="GroupsIntro">
		<ul class="groups">
			<li class="group" v-for="(group,index) in groups" :key="index">
				<h3>{{ group.name }}</h3>
				<h4>{{ group.name_en }}</h4>
				<p v-html="group.intro"></p>
				<ul class="links">
					<li v-for="(link,index) in group.links" :key="index">
						<a :href="link.url">{{ link.title }}</a>
					</li>
				</ul>
				<div class="slideCtn">
					我是 slide<br>
					我是 slide<br>
					我是 slide<br>
					我是 slide<br>
				</div>
			</li>
    	</ul>
	</section>
</template>


<script>
export default {
  props: {
    groups: {
      type: Array,
      default: () => {
        return [
			{
				name: '技术组',
				name_en: 'DEVELOPE GROUP',
				intro: 'BYR 坚强的技术后盾，新产品的研发中心。<br>希望热爱技术的小伙伴加入我们一起玩！',
				links: [
					{
						title: '计划中项目',
						url: 'http://wiki.byr.moe'
					},
					{
						title: '计划中项目',
						url: 'http://wiki.byr.moe'
					},
				],
				slides: [
					{
						text: '我们维护 BYRIO 北邮互联网与开源社区，参与贡献 KDE.org 等国际开源软件项目，还有机会和清华 TUNA 、中科大 USTCLUG 的小伙伴们一起交流。',
						img: 'slide/soscon.png'
					},
					{
						text: '我们维护 BYRIO 北邮互联网与开源社区，参与贡献 KDE.org 等国际开源软件项目，还有机会和清华 TUNA 、中科大 USTCLUG 的小伙伴们一起交流。',
						img: 'slide/soscon.png'
					}
				]
			},
			{
				name: '技术组',
				name_en: 'DEVELOPE GROUP',
				intro: 'BYR 坚强的技术后盾，新产品的研发中心。<br>希望热爱技术的小伙伴加入我们一起玩！',
				links: [
					{
						title: '计划中项目',
						url: 'http://wiki.byr.moe'
					},
					{
						title: '计划中项目',
						url: 'http://wiki.byr.moe'
					},
				],
				slides: [
					{
						text: '我们维护 BYRIO 北邮互联网与开源社区，参与贡献 KDE.org 等国际开源软件项目，还有机会和清华 TUNA 、中科大 USTCLUG 的小伙伴们一起交流。',
						img: 'slide/soscon.png'
					},
					{
						text: '我们维护 BYRIO 北邮互联网与开源社区，参与贡献 KDE.org 等国际开源软件项目，还有机会和清华 TUNA 、中科大 USTCLUG 的小伙伴们一起交流。',
						img: 'slide/soscon.png'
					}
				]
			}
        ];
      }
    }
  }
};
</script>

<style lang="stylus" scoped>
.GroupsIntro
	.groups
		position relative
		margin 10px 0
		.group
			height 500px
			box-sizing border-box
			.slideCtn
				position absolute
				left -200px
				&::before
					content ''
					display block
					position absolute
					left -100px
					top -100px
					width 500px
					height 500px
					background-image url('~static/box.png')
					background-size contain
					background-repeat no-repeat
					background-position center
</style>
