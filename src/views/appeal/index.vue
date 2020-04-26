<template>
  <div class="appeal">
    <div class="appeal_left">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>司机信息</span>
        </div>
        <div class="appeal_info">
          <dl>
            <dt>姓名：</dt>
            <dd>张三</dd>
          </dl>
          <dl>
            <dt>注册手机号：</dt>
            <dd>187098859098</dd>
          </dl>
          <dl>
            <dt>来电手机号：</dt>
            <dd>187098859098</dd>
          </dl>
        </div>
      </el-card>
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>投诉信息</span>
          <el-link class="userinfo" href="/home" type="primary">用户信息 >></el-link>
        </div>
        <div class="appeal_info">
          <dl>
            <dt>投诉次数：</dt>
            <dd>2次</dd>
          </dl>
          <dl>
            <dt>被投诉次数：</dt>
            <dd>5次</dd>
          </dl>
          <dl>
            <dt>申诉次数：</dt>
            <dd>10次</dd>
          </dl>
        </div>
      </el-card>
    </div>
    <!-- right -->
    <div class="appeal_right">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>受理中</span>
          <div class="atit">【紧急】【编号102010】【即时】【高德同步】【渠道订单号】</div>
        </div>
        <div class="artxt"><span class="gray">工单标题：</span>即时-申诉-司机申述-改派申述</div>
      </el-card>
      <el-card class="elqustion">
        <el-form label-width="100px">
          <el-form-item label="问题描述：">将来型。随时间推移与标准将会产生偏差的风险。（将来要求不变，结果变了。）比如：本月要求10万任务，按以往团队实力每个月是10万完成，可以按时间进度推进，但是
本月随时间推进越来越困难，这样的偏差即为将来型问题。</el-form-item>
          <el-form-item label="图片：">1324578890.jgp</el-form-item>
          <el-form-item label="订单号：">009913355900777</el-form-item>
          <el-form-item label="城市：">北京</el-form-item>
          <el-form-item label="关联工单：">1200  0998  9999 098</el-form-item>
        </el-form>
      </el-card>
      <div class="appeal_handle">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>工单处理</span>
          </div>
          <el-form label-width="100px">
            <el-row>
              <el-col>
                <el-form-item label="申诉结果：">
                  <el-radio v-model="result.status" :label="1">成功</el-radio>
                  <el-radio v-model="result.status" :label="2">失败</el-radio>
                </el-form-item>
                <el-form-item label="补回扣款：">
                  <el-input v-model="result.mon" /> 元
                </el-form-item>
                <el-form-item label="补回罚款：">
                  <el-input v-model="result.mon" /> 元
                </el-form-item>
                <el-form-item label="司机状态：">
                  正常/永久下线/临时下线/静默 <el-radio class="flr" v-model="result.driver_status" :label="1">解除</el-radio>
                </el-form-item>
                <el-form-item label="结果描述：" class="desc">
                  <el-input type="textarea" v-model="result.desc" maxlength="200" rows="5" show-word-limit />
                </el-form-item>
                <el-form-item label="发送短信：" class="desc">
                  <el-input type="textarea" v-model="result.desc" maxlength="150" rows="5" placeholder="请输入短信内容，最大可输入150字符。 短信签名不用填写" show-word-limit />
                </el-form-item>
                <el-button type="primary">完成</el-button>
              </el-col>
            </el-row>
          </el-form>
        </el-card>
        <el-card class="box-card beiz">
          <div slot="header" class="clearfix">
            <span>内部备注</span>
            <span class="elbutn">+ 添加备注</span>
          </div>
          <el-table :data="tableData" fit>
            <el-table-column label="序号" prop="id" align="center" />
            <el-table-column label="备注" prop="name" align="center" />
            <el-table-column label="操作人" prop="author" align="center" />
            <el-table-column label="时间" prop="create" align="center" />
          </el-table>
        </el-card>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Appeal',
  data() {
    return {
      result: {
        status: 1
      },
      tableData: [
        {id: 1, name: '创建工单', author: '操作人', create: '2020-03-09 15:07:23'},
        {id: 1, name: '创建工单', author: '操作人', create: '2020-03-09 15:07:23'},
        {id: 1, name: '创建工单', author: '操作人', create: '2020-03-09 15:07:23'},
        {id: 1, name: '创建工单', author: '操作人', create: '2020-03-09 15:07:23'},
        {id: 1, name: '创建工单', author: '操作人', create: '2020-03-09 15:07:23'},
        {id: 1, name: '创建工单', author: '操作人', create: '2020-03-09 15:07:23'}
      ]
    }
  }
}
</script>

<style>
  .appeal{
    padding: 20px;
    font-size: 14px;
  }
  .el-card{
    margin-bottom: 20px;
  }
  .userinfo{
    float: right;
  }
  .appeal_left{
    width: 330px;
    float: left;
  }
  .appeal_right{
    margin-left: 360px;
    overflow: hidden;
  }
  .appeal_info dl{
    display: flex;
    justify-content: space-between;
  }
  .appeal_info dl dt, .gray{
    color: #646466;
  }
  .atit, .flr{
    float: right;
  }
  .flr{
    padding: 10px 10% 0 0;
  }
  .artxt{
    padding: 0 0 10px 0;
  }
  .elqustion .el-form-item{
    margin-bottom: 0;
  }
  .elqustion .el-form-item__content{
    line-height: 22px;
    margin-top: 10px;
  }
  .appeal_handle .el-col{
    width: 50%;
  }
  .appeal_handle .el-input, .appeal_handle .el-textarea{
    width: 90%;
  }
  .appeal_handle .el-button {
    margin:20px 0 0 360px;
  }
  .beiz .elbutn{
    padding: 3px 5px;
    border-radius:6px;
    color: #0164FF;
    border:1px solid rgba(1,100,255,1);
    float: right;
    cursor: pointer;
  }
</style>