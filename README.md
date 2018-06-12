### 基于移动网络通讯行为的风险用户识别

######## 1. 2018-05-22 baseline 

###### 因为这学期担任实训课TA，这个比赛是实训课的作业，所以做个baseline给师弟师妹们参考，这个baseline 线下是0.80,线上成绩是0.76~0.77
###### （所以LB上有一群DM+学号的，不要惊讶，不是小号,是一群可爱的小鲜肉）




######## 2. 2018-06-12 解决方案 （初赛 3th, 复赛 15th）

##### 特征工程：
2.1 单变量数量统计特征：
  ## 统计用户 记录数，用户 不同opp_num 记录数
  ## 统计用户不同 opp_head记录 数








voice_feature = [voice_opp_num,  ## 统计用户 记录数，用户 不同opp_num 记录数
                 voice_opp_head, ## 统计用户不同 opp_head记录 数
           voice_opp_len,  ## 统计用户 不同 opp_len 的记录数
           voice_call_type, ## 统计用户不同 call_tyoe 记录数
           voice_in_out_opp_num_unique, ## 统计用户不同  in_out 下 不同 opp_num记录数
           voice_opp_len_opp_num_unique, ## 统计不同 opp_len 下 不同 opp_head 记录数
            voice_opp_len_opp_head_unique, ## 统计不同 opp_len 下不同opp_head 的记录数
            voice_call_type_opp_num_unique,  ## 统计不同call_type 下 不同opp_num 的记录数
          voice_gap_time,  ## 通话时长统计量
          voice_last_gap_time, ## 两次通话间隔统计量
        voice_each_opp_num_count, ## 对opp_num one-hot 统计记录数
                 

                ]


sms_feature = [sms_opp_num,  ## 统计用户sms 不同opp_num记录数
              sms_opp_head, ## 统计用户sms 不同opp_head 记录数
              sms_opp_len, ##统计用户 不同opp_len记录数
              sms_opp_len_opp_head_unique, ##统计用户不同opp_len 中 不同opp_head的记录数
              sms_in_out, ## 不同in_out 记录数
              sms_last_start_gap_time, ## 两次短信间隔统计量
               sms_each_day_count, ##每天的短信记录数
               sms_each_day_unique_count_opp_head, ## 每天不同的opp_head 记录数
               
                sms_in_out_opp_head_unique, ## 不同in_out 下 不同opp_head 数

                sms_each_opp_head_count, ## opp_head one-hot 统计记录数
    
               
               
               

               
              ]
#sms_feature =sms_feature+sms_opp_count

wa_feature = [

    
    wa_each_name_count, ##top 1000 wa_name 分组统计记录数

]





