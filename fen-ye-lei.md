# 分页类

CII\_Pagination 类是 CodeIgniter 框架中 CI\_Pagination 类的扩展实现方式。

内部结构

```
Class CII_Pagination{
    public $base_url = NULL;
	public $total_rows = NULL;
    public $per_page = NULL;
    public __construct(){
        // 初始化成员变量
    }
    public function initialize($config = array()){
        // 通过参数为成员变量赋值
    }
    public function create_links($cur_page = 1){
        // 生成分页字符串并返回字符串
    }
}
```

使用方法

```
// 生成对象
$this->cii_pagination = new cii_pagination();
// 设置分页控制器
$cii_pagination['base_url'] = 'http://localhost:8888/ci/index.php/welcome/index/';
// 每页数量
$cii_pagination['per_page'] = 10;
// 数据总量
$cii_pagination['total_rows'] = 56;
// 初始化CII_Pagination分页类
$this->cii_pagination->initialize($cii_pagination);
// 输出分页，参数为当前页面，通过uri获取
echo $this->cii_pagination->create_links($this->uri->segment(3));
```

性能测试

使用 CodeIgniter 框架的 CI\_Pagination 类与 CII\_Pagination 类输出相同分页结果，计算耗时。

```
<style type="text/css">
body {
  padding: 0;
  margin: 0;
  min-height: 100%;
  font-size: 12px;
  font-family: 微软雅黑, 冬青黑体, 宋体, arial;
  color: #333; }
    .view-container{
        padding: 0 10px;
    }
    .view-container .pn .pn-container {
        float: left; }
        .view-container .pn .pn-container span {
          float: left;
          margin-right: 10px;
          font-size: 14px;
          line-height: 24px; }
          .view-container .pn .pn-container span a {
            display: block;
            padding: 2px 10px;
            color: #747474;
            background-color: #EDF2F8; 
            text-decoration: none; }
            .view-container .pn .pn-container span a:hover {
              background-color: #a4bddb;
              color: #FFF; }
          .view-container .pn .pn-container span.current {
            padding: 2px 10px;
            background-color: #a4bddb;
            color: #FFF; }
    .clearfix{
        clear:both;
        float: none;
    }
</style>
<div class="view-container">
    <?php
        echo "<p>CI_Pagination: </p>";
        $this->benchmark->mark('pagination_code_start');
		$pagination['full_tag_open'] = '<div class="pn"><div class="pn-container">';
        $pagination['full_tag_close'] = '<div class="clearfix"></div></div><div class="clearfix"></div></div>';
		$pagination['first_tag_open'] = '<span>';
        $pagination['first_tag_close'] = '</span>';
		$pagination['last_tag_open'] = '<span>';
        $pagination['last_tag_close'] = '</span>';
		$pagination['next_tag_open'] = '<span>';
        $pagination['next_tag_close'] = '</span>';
		$pagination['prev_tag_open'] = '<span>';
        $pagination['prev_tag_close'] = '</span>';
		$pagination['cur_tag_open'] = '<span class="current">';
        $pagination['cur_tag_close'] = '</span>';
		$pagination['num_tag_open'] = '<span>';
        $pagination['num_tag_close'] = '</span>';
		$pagination['use_page_numbers'] = true;
        $pagination['first_link'] = '首页';
		$pagination['prev_link'] = '上一页';
        $pagination['next_link'] = '下一页';
		$pagination['last_link'] = '尾页';
        $pagination['base_url'] = 'http://localhost:8888/ci/index.php/welcome/index/';
		$pagination['per_page'] = 10;
        $pagination['total_rows'] = 56;
		$this->pagination->initialize($pagination);
		echo $this->pagination->create_links();
        $this->benchmark->mark('pagination_code_end');
		echo '<p>Time : '.$this->benchmark->elapsed_time('pagination_code_start', 'pagination_code_end', 22).'</p>';
    ?>
</div>
<hr/>
<div class="view-container">
    <?php
        echo "<p>CII_Pagination: </p>";
        $this->benchmark->mark('cii_pagination_code_start');
		$cii_pagination['base_url'] = 'http://localhost:8888/ci/index.php/welcome/index/';
        $cii_pagination['per_page'] = 10;
		$cii_pagination['total_rows'] = 56;
        $this->cii_pagination->initialize($cii_pagination);
        echo $this->cii_pagination->create_links($this->uri->segment(3));
        $this->benchmark->mark('cii_pagination_code_end');
		echo '<p>Time : '.$this->benchmark->elapsed_time('cii_pagination_code_start', 'cii_pagination_code_end', 22).'</p>';
    ?>
</div>
```

结果：

![](/assets/runtime.png)

CII\_Pagination 类生成的结果与 CI\_Pagination 类生成的结果完全一致，通过 CodeIgniter 框架的基准测试类得出 CII\_Pagination 的运行时间比 CI\_Pagination 快了近10倍。



