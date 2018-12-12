<template lang="pug">
  div.character
    div
      h1 调查员信息
      div 头像 - 上传图片
      div *姓名
      div *玩家
      div *时代背景 - 选择？
      div 职业
      div *年龄
      div *性别
      div 住地
      div 出生
    div
      h1 属性
      div
        h3 购点 或 roll点 - 5连随机roll点，选择其一？  1/2|1/5 Math.floor()
        div 力量(STR)  3d6 * 5
        div 体质(CON)  3d6 * 5
        div 体型(SIZ)  (2d6+6) * 5
        div 敏捷(DEX)  3d6 * 5
        div 外表(APP)  3d6 * 5
        div 智力(INT)  (2d6+6) * 5
        div 意志(POW)  3d6 * 5
        div 教育(EDU)  (2d6+6) * 5
        div 幸运(LUCK) 3d6 * 5
        h3 是否允许属性编辑（选择购点隐藏并允许编辑，roll点可勾选）
      div
        h3 你的角色可能
        div
          p STR <= 20 弱者，虚弱
          p STR <= 40 手无缚鸡之力
          p STR <= 60 普通人左右的力量
          p STR <= 80 搏击手的水准
          p STR < 99 一拳一个小朋友
          p STR == 99 人类极限
          p STR <= 200 超越人类之力(例如大猩猩或马)
          p STR > 200 怪物之力
        div
          p CON <= 20 常年患病在身,经常需躺下休息
          p CON <= 40 体弱易风寒
          p CON <= 60 健康
          p CON <= 80 健硕，基本不会生病
          p CON < 99 液氮洗澡爽歪歪
          p CON == 99 钢筋铁骨，人类极限
          p CON <= 200 超人
          p CON > 200 怪物之体，百毒不侵
        div
          p SIZ <= 20 孩童，身短体瘦（15kg左右）
          p SIZ <= 40 乙女身材(40kg左右)
          p SIZ <= 60 普通身高或偏瘦（65kg左右）
          p SIZ <= 80 不是高就是胖（110kg左右）
          p SIZ <= 90 体型堪比姚明(140kg左右)
          p SIZ <= 99 某方面已经是超大号了(150kg左右)
          p SIZ <= 165 马或牛（436kg左右）
          p SIZ <= 200 记录中最重的人类（634kg左右）
          p SIZ > 200 650kg以上
        div
          p DEX <= 20 无法行动自如
          p DEX <= 40 腿脚不灵活(通风？)
          p DEX <= 60 普通人水平
          p DEX <= 80 运动健将
          p DEX < 99 跑得比香港记者还快
          p DEX == 99 人类极限 博尔特？
          p DEX <= 200 四脚以上
          p DEX > 200 闪电侠
        div
          p APP <= 20 挫｡估计是因为受伤事故或先天如此
          p APP <= 40 堪堪入目
          p APP <= 60 普通至极或些许清秀
          p APP <= 80 柳眉丹凤，仪表堂堂
          p APP < 99 沉鱼落雁，闭月羞花
          p APP == 99 人类极限
          p APP > 99 不存在的
        div
          p INT <= 20 只能理解最常用的数字
          p INT <= 40 思维比别人慢一拍
          p INT <= 60 有着普通人的灵光一现
          p INT <= 80 可以进行简单的发明
          p INT < 99 超凡之脑,可以理解多门语言或法则
          p INT == 99 人类极限｡天才(爱因斯坦､达芬奇､特斯拉等等)｡
          p INT <= 210 超越人类之智
          p INT > 210 怪物之智,可以理解并操作多重次元
        div
          p POW <= 20 经常成为高智力或高意志人士的人偶或玩物
          p POW <= 40 些许主见，但仍盲从
          p POW <= 60 如常人一般会有一定自制力
          p POW <= 80 我心如铁，心坚石穿
          p POW <= 100 坚强的心,对沟通不可视之物和魔法有着高潜质
          p POW <= 120 钢铁之心,与灵能领域和不可视世界有着强烈的链接｡
          p POW <= 210 超越人类,基本上是异界存在
          p POW > 210 怪物的魔法潜质和力量,超越凡人之理解力
        div
          p EDU <= 20 任何方面都没有受过教育
          p EDU <= 40 小学毕业
          p EDU <= 60 高中毕业
          p EDU <= 70 大学毕业(专科学位)
          p EDU <= 80 是重点大学的学生，或是普通大学的研究生
          p EDU <= 90 博士学位,教授
          p EDU < 99 某研究领域的世界级权威
          p EDU == 99 人类极限
          p EDU > 99 不存在的
        div
          p LUCK <= 20 克夫克妻
          p LUCK <= 40 霉运连连
          p LUCK <= 60 命格平庸
          p LUCK <= 80 升职加薪顺风顺水
          p LUCK < 99 会被彩票店拒之门外
          p LUCK == 99 幸运女神私生子
          p LUCK > 99 未知领域
      div
        h3 伤害加值（Damage Bonus）、体格（Build）
        div STR+CON= 2-64     -2    -2
        div STR+CON= 65-84    -1    -1
        div STR+CON= 85-124   0     0
        div STR+CON= 125-164  +1d4  1
        div STR+CON= 165-204  +1d6  2
        div STR+CON= 205-284  +2d6  3
        div STR+CON= 285-364  +3d6  4
        div STR+CON= 365-444  +4d6  5
        div STR+CON= 445-524  +5d6  6
      div
        h3 移动速度（MOV）
        div DEX、STR < SIZ     7
        div DEX || STR >= SIZ  8
        div DEX、STR >= SIZ    9
      div 生命值(Hit Points)  Math.floor(CON+SIZ / 10)
      div 理智(Sanity) POW
      div 魔法(Magic Points) POW/5
      div
        h3 是否需要年龄调整
        div 15-19
          p STR、CON 合计 -5
          p EDU - 5
          p LUCK再roll一次取高值
        div 20-39
          p EDU 1次增强检定（1d100 > EDU ? EDU += 1d10 : EDU; EDU = Math.min(EDU, 99);）
        div 40-49
          p EDU 2次增强检定
          p STR、CON、DEX 合计 -5
          p APP -5
          P MOV -1
        div 50-59
          p EDU 3次增强检定
          p STR、CON、DEX 合计 -10
          p APP -10
          P MOV -2
        div 60-69
          p EDU 4次增强检定
          p STR、CON、DEX 合计 -20
          p APP -15
          P MOV -3
        div 70-79
          p EDU 4次增强检定
          p STR、CON、DEX 合计 -40
          p APP -20
          P MOV -4
        div 80-89
          p EDU 4次增强检定
          p STR、CON、DEX 合计 -80
          p APP -25
          P MOV -5
    div
      h1 职业（信用范围、剩余职业点、技能点 INT*2）
      h3 职业选择（标色吧，区分职业技能和兴趣，信用评级标为职业技能）
      h3 技能列表（格斗、射击 需要细化分支才可加点， 时代背景不是现代 【计算机使用】和【电子学】隐藏）
      div 自设技能留空
      h3 资产
      div 信誉参考
        div <= 0 身无分文   连贫穷都够不上的人才能够叫做身无分文。
          p 住所：大概只有睡大街。
          p 旅行：步行，扒车或逃票上火车轮船。
        div < 10 贫穷   刚好买得起最廉价的屋顶，每天能够吃到一餐廉价食物
          p 住所：最最最廉价的出租屋或睡袋旅馆。
          p 旅行：最便宜的公众运输方式。反正只要赶便宜就对了，与之相伴的是不可靠。
        div < 49  标准   舒适的生活水平，一日三餐，偶尔下馆子。
          p 住所：普通的家或公寓，并关租赁还是自购。外出住普通的旅馆。
          p 旅行：会使用普通的旅行方式，不会用最高级。在现代来看，大概会有一辆自己的小车。
        div < 89 小康   小康级别已经可以享受奢侈品的舒适了。
          p 住所：真材实料的住地，也许会有一些仆人（管家，主妇，清洁工，园丁，等等）。乡下估计还有小别墅。会住昂贵的宾馆。
          p 旅行：头等舱。会买高档车或同等的交通工具。
        div < 98 富裕   富裕级别就是享受超级奢侈品的时候了。
          p 住所：豪华住所和有着大量仆人的庭院（管家，女仆，洗妇，园丁等等）。乡下和别处有着别墅是定番。住总统套房。
          p 旅行：头等舱。现代社会估摸还会有很多豪车。没有必要因为调查员的生活水平而花时间详细计算住所、饮食和交通。如果调查员想要进行有意义的购买，请看资产对照表。
        div == 99  豪富   与富裕差不多，但钱已经只是一个代号了。你将是世界上最富有的人。
    div
      h1 背景、经历相关、
      div
        h3 背景故事 - 选填
        div 个人描述
        div 思想/信念
        div 重要之人
        div 意义非凡之地
        div 宝贵之物
        div 特点
        div 损伤&伤痕
        div 恐惧&狂躁
        div 背景故事
      h3 调查员伙伴
      h3 调查员经历
      div
        h3 克苏鲁神话
        div 古籍、魔法相关
        div 第三类接触
    div
      h1 其他 - 路由？
      h3 职业列表速查
      h3 武器列表速查
      h3 资产对照表
      h3 疯狂标速查
      h3 KP帷幕里一些东西
    div
      h1 成卡 打印版面或者txt下载
      h3 是否需要服务器保存
</template>

<script>
export default {
  name: 'Character',
  data () {
    return {
    }
  }
}
</script>

<style lang="less">
</style>
