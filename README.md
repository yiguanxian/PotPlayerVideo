video.oncontextmenu = function(e){
  e.preventDefault()
}
阻止在视频上右键单击鼠标可以选择浏览器自带的控件


setInterval(function(){
  canPlay.style.width = video.buffered.end(0) / video.duration * 100 + "%"
},50)
video.buffered.end(0)就是缓冲的结尾部分，返回值单位是s，类型为number。video.duration就是该视频的总长度。缓冲的部分 / 总长度 可以得到缓冲部分相对于时间轴的宽度。


video.addEventListener('waiting',function(){}
监听当缓冲不足以播放视频时，我们可以在这个方法下进行设置，例如过场动画。


video.addEventListener('playing',function(){}
监听缓冲足够播放视频时，我们可以在这个方法下设置，譬如取消过场动画。


function getVideoTime(time){
  var arr = []
  var hours = parseInt(time / 60 / 60)
  hours = hours < 10 ? '0' + hours : hours
  var miniutes = parseInt(time / 60 % 60)
  miniutes = miniutes < 10 ? '0' + miniutes : miniutes
  var seconds = parseInt(time % 60)
  seconds = seconds < 10 ? '0' + seconds : seconds
  arr.push(hours,miniutes,seconds)
  return arr
}
封装的时间格式化方法。video.duration以及video.currentTime返回值都是带小数点的数字，我们需要将这些数字转换为时：分：秒的形式。这里返回值是一个数组。

示例：https://zhouwuchao.github.io/


