<template>
    <div>
      
			
			<p>Please fill in the information！</p>
			<div class="panel panel-default">
				<div class="panel-header">Register Form</div>
				<div class="panel-body">
					<form action="" method="post" class="form form-horizontal responsive" id="demoform">
						<div class="row cl">
							<label class="form-label col-xs-3">Email：</label>
							<div class="formControls col-xs-8">
								<input type="text" class="input-text" placeholder="@" name="email" id="email" autocomplete="on">
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">name：</label>
							<div class="formControls col-xs-8">
								<input type="text" class="input-text" placeholder="Ye Yichen" name="username" id="username">
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">Handphone：</label>
							<div class="formControls col-xs-8">
								<input type="text" class="input-text" autocomplete="off" placeholder="Handphone" name="telephone" id="telephone">
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">Workphone：</label>
							<div class="formControls col-xs-8">
								<input type="password" class="input-text" autocomplete="off" placeholder="Workphone" name="password" id="password">
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">密码验证：</label>
							<div class="formControls col-xs-8">
								<input type="password" class="input-text" autocomplete="off" placeholder="密码" name="password2" id="password2">
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">单选框：</label>
							<div class="formControls skin-minimal col-xs-5">
								<div class="radio-box">
									<input type="radio" id="sex-1" name="sex">
									<label for="sex-1">male</label>
								</div>
								<div class="radio-box">
									<input type="radio" id="sex-2" name="sex">
									<label for="sex-2">female</label>
								</div>
								<div class="radio-box">
									<input type="radio" id="sex-3" name="sex">
									<label for="sex-3">保密</label>
								</div>
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">出生日期：</label>
							<div class="formControls col-xs-8">
								<input type="text" class="input-text datetimepicker-input" value="" autocomplete="off" id="datetimepicker" name="datetimepicker">
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">爱好：</label>
							<div class="formControls skin-minimal col-xs-5">
								<div class="check-box">
									<input type="checkbox" id="checkbox-5" name="checkbox2">
									<label for="checkbox-5">上网</label>
								</div>
								<div class="check-box">
									<input type="checkbox" id="checkbox-6" name="checkbox2">
									<label for="checkbox-6">摄影</label>
								</div>
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">数量：</label>
							<div class="formControls skin-minimal col-xs-5">
								<div id="spinner-demo"></div>
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">attachment：</label>
							<div class="formControls col-xs-8">
								<span class="btn-upload form-group">
								<input class="input-text upload-url" type="text" name="uploadfile-2" id="uploadfile-2" readonly style="width:200px">
								<a href="javascript:void();" class="btn btn-primary upload-btn"><i class="Hui-iconfont">&#xe642;</i> Browse</a>
								<input type="file" multiple name="file-2" class="input-file">
								</span>
							</div>
						</div>
						<div class="row clearfix">
							<label class="form-label col-xs-3">Choose a area：</label>
							<div class="formControls col-xs-8">
								<div class="row clearfix" style="margin-top:0">
									<div class="col-xs-6">
										<span class="select-box">
											<select class="select" size="1" name="city">
												<option value="" selected>选择省份</option>
												<option value="1">北京</option>
												<option value="2">上海</option>
												<option value="3">广州</option>
											</select>
										</span>
									</div>
									<div class="col-xs-6">
										<span class="select-box">
											<select class="select" size="1" name="city">
												<option value="" selected>选择城市</option>
												<option value="1">北京</option>
												<option value="2">上海</option>
												<option value="3">广州</option>
											</select>
										</span>
									</div>
								</div>
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">网址：</label>
							<div class="formControls col-xs-8">
								<input type="text" class="input-text" placeholder="http://" name="website" id="website">
							</div>
						</div>
						<div class="row cl">
							<label class="form-label col-xs-3">comments：</label>
							<div class="formControls col-xs-8">
								<textarea cols="" rows="" class="textarea" name="beizhu" id="beizhu"  placeholder="anything need to follow up with this person"></textarea>
							</div>
						</div>
						<div class="row cl">
							<div class="col-xs-8 col-xs-offset-3">
								<input class="btn btn-primary" type="submit" value="&nbsp;&nbsp;提交&nbsp;&nbsp;">
							</div>
						</div>
					</form>
				</div>
			</div>
	
    </div>


</template>

	<script>
export default {
  name: "PeopleRegister"
};
</script>