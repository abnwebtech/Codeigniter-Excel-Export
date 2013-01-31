Codeigniter-Excel-Export
========================

An Codeigniter library for exporting the data from database to Excel file. 

一个用于导出数据库数据到Excel文件的PHP库，用于Codeigniter框架中。(支持Excel中包含中文文字)

使用方法:
========================

1. 复制Excel.php到相应目录(application/libraries目录下)
------------------------

2. 创建数据结果集
------------------------

<?php
public function export() {
    $this->load->library('excel');

    $sql = $this->db->get('dbtable');

    $this->excel->filename = 'abc123';
    $this->excel->make_from_db($sql);
}
?>

3. 导出到Excel文
--------------------------

<?php
public function export() {
    $titles = array('
        'field1', 'field2', 'field3'
    ');
    $array = array();
    for ($i = 0; $i <= 100; $i++) {
        $array[] = array($i, $i+1, $i+2);
    }
    $this->excel->make_from_array($titles, $array);
}
?>

参考项目
=========================

https://github.com/EllisLab/CodeIgniter/wiki/Excel-Plugin

https://github.com/JOakley77/CI-Excel-Generation-Library




