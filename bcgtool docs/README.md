{{content}}:content is injected
((content)):content that real matters

    Usage: ./bin/bcgtool.sh [-e|-d|-n] [-i|-p|-v] [-a]
    -e indicates the directory of the output file
    -d indicates the directory of the filter file
    -n indicates the subnet
    -i indicates the directory of the input file
    -p indicates the plan name of the config
    -v indicates version
    -a indicates activating the plan name


Use Case1: Report

	CMD:
	
	/opt/ericsson/nms_umts_wran_bcg/bin/bcgtool.sh \
	 -e /var/opt/ericsson/nms_umts_wran_bcg/files/export/((Report_2015-08-28_12-21-04.xml)) \
	 -d ~/ReportFilterPA3.xml \
	 -n "SubNetwork=ONRM_ROOT_MO_R,MeContext=eNB9 SubNetwork=ONRM_ROOT_MO_R,MeContext=eNB10 SubNetwork=ONRM_ROOT_MO_R,MeContext=eNB4341 SubNetwork=ONRM_ROOT_MO_R,MeContext=eNB1011 SubNetwork=ONRM_ROOT_MO_R,MeContext=eNB_4_319"

	Response:
	
	Included global environment settings
	Included local environment settings
	Report file not requested, logging will be directed to the console
	WFWK TRACING directed to LogAgent. trace.target not set
	OP: 09/06/15 15:45:57   About to start CLI export
	OP: 09/06/15 15:45:57   Export File: test_export1.xml already exists. This is backed up as: test_export1.xml.bck
	OP_START: 09/06/15 15:45:58     CLI export started successfully
	OP_PROGRESS: 09/06/15 15:45:58  Error log location for export is /var/opt/ericsson/nms_umts_wran_bcg/logs/export/{{ErrLog_Report_2015-08-28_12-21-04.xml}}
	OP_PROGRESS: 09/06/15 15:45:58  Error Info log location for export is /var/opt/ericsson/nms_umts_wran_bcg/logs/export/ErrLog_Report_2015-08-28_12-21-04.xml
	OP_PROGRESS: 09/06/15 15:46:00  The export operation has succeeded with 32 MOs exported
	OP_STATUS: 09/06/15 15:46:00    Export has succeeded
	OP: 09/06/15 15:46:00   An existing export file was backed up during this operation.
	Previously existing export file was renamed to :/var/opt/ericsson/nms_umts_wran_bcg/files/export/test_export1.xml.bck
	OP_END: 09/06/15 15:46:00       Export operation has ended

	Download errLog
	 
 
Use Case2: Config

	CMD:
	/opt/ericsson/nms_umts_wran_bcg/bin/bcgtool.sh -i /home/emoselm/esheday/Lock_2015-08-28_12-21-04.xml -p Plan_Lock_2015-08-28_12-21-04 -v
	/opt/ericsson/nms_umts_wran_bcg/bin/bcgtool.sh -a Plan_Lock_2015-08-28_12-21-04
	/opt/ericsson/nms_umts_wran_bcg/bin/bcgtool.sh -i /home/emoselm/esheday/Config_2015-08-28_12-21-04.xml -p Plan_Config_2015-08-28_12-21-04 -v
	/opt/ericsson/nms_umts_wran_bcg/bin/bcgtool.sh -a Plan_Config_2015-08-28_12-21-04
	/opt/ericsson/nms_umts_wran_bcg/bin/bcgtool.sh -i /home/emoselm/esheday/Unlock_2015-08-28_12-21-04.xml -p Plan_Unlock_2015-08-28_12-21-04 -v
	/opt/ericsson/nms_umts_wran_bcg/bin/bcgtool.sh -a Plan_Unlock_2015-08-28_12-21-04


	Response:
	
	Included global environment settings
	Included local environment settings
	Report file not requested, logging will be directed to the console
	WFWK TRACING directed to LogAgent. trace.target not set
	OP: 08/06/15 16:44:54   Plan name = {{Plan_Config_2015-08-28_12-21-04}}, file path = {{/home/emoselm/esheday/Config_2015-08-28_12-21-04.xml}}
	OP: 08/06/15 16:44:54   About to start CLI import
	OP: 08/06/15 16:44:55   Resolved import sesssion factory OK
	OP_PROGRESS: 08/06/15 16:44:55  The import file is being transfered to default import directory from: {{/home/emoselm/esheday/Config_2015-08-28_12-21-04.xml}}
	OP: 08/06/15 16:44:56   PrepareMOImport called successfully
	OP_START: 08/06/15 16:44:56     CLI import started successfully
	OP: 08/06/15 16:44:56   Waiting for callback latch!
	OP_PROGRESS: 08/06/15 16:44:56  Error log location for import is /var/opt/ericsson/nms_umts_wran_bcg/logs/import/{{errLog_Config_2015-08-28_12-21-04.xml}}
	OP_PROGRESS: 08/06/15 16:44:56  Error Info log location for import is /var/opt/ericsson/nms_umts_wran_bcg/logs/import/errLog_Config_2015-08-28_12-21-04.xml
	OP_PROGRESS: 08/06/15 16:44:56  Total MOs to be imported is 1
	OP_PROGRESS: 08/06/15 16:44:56  Number of MOs successfully imported so far is 0, Number of MOs unsuccessfully imported so far is 0, from a total of 1
	OP_PROGRESS: 08/06/15 16:44:57  Number of MOs successfully imported so far is 1, Number of MOs unsuccessfully imported so far is 0, from a total of 1
	OP_PROGRESS: 08/06/15 16:44:57  Number of MOs successfully imported so far is 1, Number of MOs unsuccessfully imported so far is 0, from a total of 1
	OP_PROGRESS: 08/06/15 16:44:57  Number of MOs successfully imported so far is 1, Number of MOs unsuccessfully imported so far is 0, from a total of 1
	OP_PROGRESS: 08/06/15 16:44:57  The import operation has succeeded, all 1 MOs imported successfully
	OP_STATUS: 08/06/15 16:44:57    Import has succeeded
	OP: 08/06/15 16:44:57   End waiting for callback latch!
	OP_END: 08/06/15 16:44:57       Import operation has ended
	OP: 08/06/15 16:44:57   Resolved import sesssion factory OK

	
	Download errLog is similar with Report

Use Case3: Active

	CMD:
    
	/opt/ericsson/nms_umts_wran_bcg/bin/bcgtool.sh -a Plan_Config_2015-08-28_12-21-04
	 
	Response:
	
	Included global environment settings
	Included local environment settings
	Report file not requested, logging will be directed to the console
	OP: 09/06/15 10:28:04   About to start CLI activation
	OP_END: 09/06/15 10:28:09       Activation progress 82% for plan {{Plan_Config_2015-08-28_12-21-04}}
	OP_END: 09/06/15 10:28:11       Activation progress 100% for plan {{Plan_Config_2015-08-28_12-21-04}}
	OP_END: 09/06/15 10:28:11       Activation SUCCESSFUL for plan {{Plan_Config_2015-08-28_12-21-04}}
	OP_END: 09/06/15 10:28:11       Status for node SubNetwork=ONRM_ROOT_MO_R,MeContext=eNB9 is COMPLETE
	OP_END: 09/06/15 10:28:11       Activation operation has ended
