# Next-generation-sequencing

## 测试机器
Mac M2
- vcpu 8
- memory 16G
## 安装程序
- python 3.12
- Bio 1.7.1
- cutadapt 4.9
- vsearch v2.30.0
- FastQC v0.12.1
- trimmomatic 0.39
## 注意事项
- 使用前只需要将strict_QC命令中的文件路径更改为自己的即可，其他都不需要动
- strict_QC命令中的文件路径必须正确(/home是根路径，错误用法示例：./home)
- strict_QC命令中的文件名称要看清（是fq还是fq.gz）
- strict_QC命令中的文件名称避开F.fq.gz 和 R.fq.gz（该命令运行结束后会生成F.fq.gz 和 R.fq.gz，防止重复）
## 文件输出目录
- strict_QC命令结束后获得经过严格处理的数据
    - strict_QC('文件F的路径', '文件R的路径', '严格处理后的文件保存路径', primer_f="", primer_r=""）
- NGS命令结束后获得所有文件
  - F和R合并后的文件路径：严格处理后的文件保存路径/merged.fasta
  - 再次质量检测后的文件夹路径：严格处理后的文件保存路径/fastqc_output
  - 再次质控后的fasta文件：严格处理后的文件保存路径/output_trimmed.fastq
  - 针对spacer定位的区域进行扫描后的文件路径：严格处理后的文件保存路径
## 运行
依次执行
