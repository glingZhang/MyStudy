>https://blog.csdn.net/LZGS_4/article/details/43206285

<span style="font-family:SimSun;font-size:18px;">var oId = 1;
$('#single').click(function(){
$('#single-answer').clone(true).attr('id','single-answer'+oId).appendTo('#single-answer-null').show();
	oId += 1;
});
</span>

