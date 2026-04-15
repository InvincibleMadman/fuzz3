# libiec61850 server_example_basic_io AFL++ seed corpus

这些 .bin 文件适用于“stdin -> 本地 TCP 回灌 -> IedServer 真实 TCP 监听入口”的 harness。

## 文件列表

- `00_cr_only.bin` (22 bytes): 仅 COTP CR，覆盖 listen/accept/COTP 入口。
- `01_cr_initiate.bin` (233 bytes): CR + MMS Initiate，进入 ACSE/Presentation/MMS 关联路径。
- `02_cr_initiate_identify.bin` (260 bytes): 关联后立刻 Identify。
- `03_assoc_identify_vmd_namelist.bin` (296 bytes): Identify + GetNameList(vmdSpecific)。
- `04_assoc_domain_namelist.bin` (313 bytes): GetNameList(domainSpecific=simpleIOGenericIO)。
- `05_assoc_domain_namelist_continue.bin` (335 bytes): 带 continueAfter 的域内枚举。
- `06_assoc_read_vendor.bin` (343 bytes): 读 GGIO1$DC$NamPlt$vendor。
- `07_assoc_read_analogs.bin` (489 bytes): 批量读 4 路模拟量。
- `08_assoc_read_statuses.bin` (676 bytes): 批量读 4 路状态量 stVal/t。
- `09_assoc_getvaa_vendor.bin` (334 bytes): GetVariableAccessAttributes(vendor)。
- `10_assoc_getvaa_anin1.bin` (332 bytes): GetVariableAccessAttributes(AnIn1.mag.f)。
- `11_assoc_write_vendor.bin` (350 bytes): 写 vendor VisibleString。
- `12_assoc_write_GGIO1_CO_SPCSO1_ctlVal.bin` (343 bytes): 写 GGIO1$CO$SPCSO1$ctlVal BOOLEAN。
- `13_assoc_write_GGIO1_CO_SPCSO2_ctlVal.bin` (343 bytes): 写 GGIO1$CO$SPCSO2$ctlVal BOOLEAN。
- `14_assoc_write_GGIO1_CO_SPCSO3_ctlVal.bin` (343 bytes): 写 GGIO1$CO$SPCSO3$ctlVal BOOLEAN。
- `15_assoc_write_GGIO1_CO_SPCSO4_ctlVal.bin` (343 bytes): 写 GGIO1$CO$SPCSO4$ctlVal BOOLEAN。
- `16_assoc_write_GGIO1_CO_SPCSO1_Oper_ctlVal.bin` (348 bytes): 写 GGIO1$CO$SPCSO1$Oper$ctlVal BOOLEAN。
- `17_assoc_write_GGIO1_CO_SPCSO2_Oper_ctlVal.bin` (348 bytes): 写 GGIO1$CO$SPCSO2$Oper$ctlVal BOOLEAN。
- `18_assoc_write_GGIO1_CO_SPCSO3_Oper_ctlVal.bin` (348 bytes): 写 GGIO1$CO$SPCSO3$Oper$ctlVal BOOLEAN。
- `19_assoc_write_GGIO1_CO_SPCSO4_Oper_ctlVal.bin` (348 bytes): 写 GGIO1$CO$SPCSO4$Oper$ctlVal BOOLEAN。
- `20_assoc_read_events_dataset.bin` (328 bytes): 按 variableListName 读 LLN0$Events。
- `21_assoc_define_newdataset.bin` (517 bytes): 定义 LLN0$newDataSet。
- `22_assoc_get_events_nvl_attr.bin` (321 bytes): 读取 LLN0$Events 属性。
- `23_assoc_newdataset_roundtrip.bin` (726 bytes): create -> getattr -> read -> delete 的动态数据集往返。
- `27_assoc_getvaa_LLN0_RP_EventsRCB.bin` (329 bytes): GetVariableAccessAttributes(LLN0$RP$EventsRCB)。
- `28_assoc_read_LLN0_RP_EventsRCB.bin` (338 bytes): 读取 LLN0$RP$EventsRCB。
- `29_assoc_getvaa_LLN0_BR_EventsRCB.bin` (329 bytes): GetVariableAccessAttributes(LLN0$BR$EventsRCB)。
- `30_assoc_read_LLN0_BR_EventsRCB.bin` (338 bytes): 读取 LLN0$BR$EventsRCB。
- `31_assoc_read_bad_object.bin` (342 bytes): 读不存在对象，覆盖错误返回分支。
- `32_assoc_mixed_deep.bin` (1559 bytes): 单连接混合会话：Identify + NameList + Read + Write + NVL。
- `41_malformed_short_tpkt.bin` (7 bytes): 极短 TPKT/COTP。
- `42_malformed_overlong_tpkt_len.bin` (15 bytes): TPKT 长度字段异常过大。
- `43_malformed_bad_ber_length.bin` (292 bytes): BER 长度字段不一致。
- `44_malformed_deep_sequence.bin` (365 bytes): 深层嵌套 Sequence。
- `45_malformed_unknown_service.bin` (290 bytes): 未知 confirmed service tag。
- `46_malformed_empty_confirmed.bin` (282 bytes): 空 confirmed PDU。