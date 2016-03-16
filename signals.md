# Signals

|	Subsystem	|	Name	|	Range	|	Output	|	Pins	|	Connector 	|	Card	|	Rate (Hz)	|	Current PXI Slot	|	Description	|
|	-------------	|	--------	|	---------	|	---------	|	------	|	------------	|	--------	|	------------	|	--------------------	|	-------------------	|
|	PAS	|	Speaker Out	|	0-10 V	|	AO0	|	55,21	|	0	|	7842R	|	80k	|	8	|	Runs a speaker signal from 0 to 10 V at the maximum range.	|
|		|	LaserOut 0	|	 -10-10 V	|	AO1	|	54,20	|	0	|	7842R	|	40k	|	8	|	Laser drive signal for cell 0	|
|		|	LaserOut 1	|	 -10-10 V	|	AO2	|	53,19	|	0	|	7842R	|	40k	|	8	|	Laser drive signal for cell 1	|
|		|	LaserOut 2	|	 -10-10 V	|	AO3	|	52,18	|	0	|	7842R	|	40k	|	8	|	Laser drive signal for cell 2	|
|		|	LaserOut 3	|	 -10-10 V	|	AO4	|	51,17	|	0	|	7842R	|	40k	|	8	|	Laser drive signal for cell 3	|
|		|	LaserOut 4	|	 -10-10 V	|	AO5	|	50,16	|	0	|	7842R	|	40k	|	8	|	Laser drive signal for cell 4	|
|		|	Speaker Enable	|	TTL	|	DIO10	|	11,9	|	0	|	7842R	|	N/A	|	8	|	Switch between speaker and laser output.  High == speaker.	|
|		|	iSpk Enable 0	|	TTL	|	DIO0	|	36,8	|	0	|	7842R	|	N/A	|	8	|	Individual cell 0 enable signal for the speaker.  High indicates that speaker is not powered.	|
|		|	iSpk Enable 1	|	TTL	|	DIO1	|	37,8	|	0	|	7842R	|	N/A	|	8	|	Individual cell 1 enable signal for the speaker.  High indicates that speaker is not powered.	|
|		|	iSpk Enable 2	|	TTL	|	DIO2	|	38,8	|	0	|	7842R	|	N/A	|	8	|	Individual cell 2 enable signal for the speaker.  High indicates that speaker is not powered.	|
|		|	iSpk Enable 3	|	TTL	|	DIO3	|	39,8	|	0	|	7842R	|	N/A	|	8	|	Individual cell 3 enable signal for the speaker.  High indicates that speaker is not powered.	|
|		|	iSpk Enable 4	|	TTL	|	DIO4	|	40,8	|	0	|	7842R	|	N/A	|	8	|	Individual cell 4 enable signal for the speaker.  High indicates that speaker is not powered.	|
|		|	Laser Enable 0	|	TTL	|	DIO5	|	41,8	|	0	|	7842R	|	N/A	|	8	|	Laser enable signal for cell 0.  High == laser powered.	|
|		|	Laser Enable 1	|	TTL	|	DIO6	|	42,8	|	0	|	7842R	|	N/A	|	8	|	Laser enable signal for cell 1.  High == laser powered.	|
|		|	Laser Enable 2	|	TTL	|	DIO7	|	43,8	|	0	|	7842R	|	N/A	|	8	|	Laser enable signal for cell 2.  High == laser powered.	|
|		|	Laser Enable 3	|	TTL	|	DIO8	|	10,8	|	0	|	7842R	|	N/A	|	8	|	Laser enable signal for cell 3.  High == laser powered.	|
|		|	Laser Enable 4	|	TTL	|	DIO9	|	44,8	|	0	|	7842R	|	N/A	|	8	|	Laser enable signal for cell 4.  High == laser powered.	|
|		|	Microphone 0	|		|	AI0	|	68,34	|	0	|	7842R	|	40k	|	8	|	Microphone signal for cell 0	|
|		|	Microphone 1	|		|	AI1	|	66,32	|	0	|	7842R	|	40k	|	8	|	Microphone signal for cell 1	|
|		|	Microphone 2	|		|	AI2	|	65,31	|	0	|	7842R	|	40k	|	8	|	Microphone signal for cell 2	|
|		|	Microphone 3	|		|	AI3	|	63,29	|	0	|	7842R	|	40k	|	8	|	Microphone signal for cell 3	|
|		|	Microphone 4	|		|	AI4	|	62,28	|	0	|	7842R	|	40k	|	8	|	Microphone signal for cell 4	|
|		|	Photodiode 0	|		|	AI0	|	0,8	|	0	|	6225	|	40k	|	6	|	Photodiode signal for cell 0	|
|		|	Photodiode 1	|		|	AI1	|	1,9	|	0	|	6225	|	40k	|	6	|	Photodiode signal for cell 1	|
|		|	Photodiode 2	|		|	AI2	|	2,10	|	0	|	6225	|	40k	|	6	|	Photodiode signal for cell 2	|
|		|	Photodiode 3	|		|	AI3	|	3,11	|	0	|	6225	|	40k	|	6	|	Photodiode signal for cell 3	|
|		|	Photodiode 4	|		|	AI4	|	4,12	|	0	|	6225	|	40k	|	6	|	Photodiode signal for cell 4	|
|		|	Laser RMS 0	|		|	AI5	|	5,13	|	0	|	6225	|	40k	|	6	|	Laser RMS signal for cell 0	|
|		|	Laser RMS 1	|		|	AI6	|	6,14	|	0	|	6225	|	40k	|	6	|	Laser RMS signal for cell 1	|
|		|	Laser RMS 2	|		|	AI16	|	16,24	|	1	|	6225	|	40k	|	6	|	Laser RMS signal for cell 2	|
|		|	Laser RMS 3	|		|	AI17	|	17,25	|	1	|	6225	|	40k	|	6	|	Laser RMS signal for cell 3	|
|		|	Laser RMS 4	|		|	AI18	|	18,26	|	1	|	6225	|	40k	|	6	|	Laser RMS signal for cell 4	|
|		|	Tcell_00	|		|	AI19	|	19,27	|	1	|	6225	|	40k	|	6	|	Cell 0, thermistor 0	|
|		|	Tcell_01	|		|	AI20	|	20,28	|	1	|	6225	|	40k	|	6	|	Cell 0, thermistor 1	|
|		|	Tcell_10	|		|	AI21	|	21,29	|	1	|	6225	|	40k	|	6	|	Cell 1, thermistor 0	|
|		|	Tcell_11	|		|	AI22	|	22,30	|	1	|	6225	|	40k	|	6	|	Cell 1, thermistor 1	|
|		|	Tcell_20	|		|	AI23	|	23,31	|	1	|	6225	|	40k	|	6	|	Cell 2, thermistor 0	|
|		|	Tcell_21	|		|	AI32	|	32,40	|	1	|	6225	|	40k	|	6	|	Cell 2, thermistor 1	|
|		|	Tcell_30	|		|	AI33	|	33,41	|	1	|	6225	|	40k	|	6	|	Cell 3, thermistor 0	|
|		|	Tcell_31	|		|	AI34	|	34,42	|	1	|	6225	|	40k	|	6	|	Cell 3, thermistor 1	|
|		|	Tcell_40	|		|	AI35	|	35,43	|	1	|	6225	|	40k	|	6	|	Cell 4, thermistor 0	|
|		|	Tcell_41	|		|	AI36	|	36,44	|	1	|	6225	|	40k	|	6	|	Cell 4, thermistor 1	|
|		|	Denuded Bypass	|		|	P0.0	|	52,18	|	0	|	6225	|	On Demand	|	6	|	These valves control the flow through the denuded channel of the PAS - whether the flow will bypass the denuder or go through it.	|
|		|		|		|	P0.1	|	17,18	|	0	|		|		|	6	|		|
|	General	|	Filter CMD	|		|	P0.0	|		|	0	|	6225	|	On Demand	|	7	|	These valves control whether the flow will be sample or through the filter.	|
|		|		|		|	P0.1	|		|	0	|		|		|	7	|		|
|		|	Filter Rtn	|		|	P0.5	|		|	0	|		|		|	7	|	These digital IO are feedback for current filter position.	|
|		|		|		|	P0.6	|		|	0	|		|		|	7	|		|
|		|	Cabin CMD	|		|	P0.2	|		|	0	|	6225	|	On Demand	|	7	|	These valves control where the main flow comes from - through the pressure controller and cabin inlet or through the aerosol inlet.	|
|		|		|		|	P0.3	|		|	0	|		|		|	7	|		|
|		|	Cabin Rtn	|		|	P1.0	|		|	0	|		|		|	7	|	These DIO are feedback for the current cabin valve position.	|
|		|		|		|	P1.1	|		|	0	|		|		|	7	|		|
|		|	O3	|		|	P0.4	|		|	0	|	6225	|	On Demand	|	7	|	O3 addition valve	|
|		|	Inlet LED	|		|	P1.4	|	41,7	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Filter LED	|		|	P2.1	|	3,4	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Denuder LED	|		|	P2.2	|	45,12	|	0	|	6225	|	On Demand	|	6	|		|
|		|	O3 LED	|		|	P2.3	|	46,12	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Spk LED	|		|	P2.4	|	2,4	|	0	|	6225	|	On Demand	|	6	|		|
|		|	405 LED	|		|	P2.5	|	40,7	|	0	|	6225	|	On Demand	|	6	|		|
|		|	515 LED	|		|	P2.6	|	1,35	|	0	|	6225	|	On Demand	|	6	|		|
|		|	660 LED	|		|	P2.7	|	39,4	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Error	|		|	P0.2	|	49,15	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Heartbeat	|		|	P0.3	|	47,13	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Sample Pump Enable	|		|	P0.4	|	19,53	|	0	|	6225	|	On Demand	|	6	|		|
|		|	O3 Generator Enable	|		|	P0.5	|	51,18	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Denuder Enable	|		|	P0.6	|	16,50	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Laser PS Enable	|		|	P0.7	|	48,15	|	0	|	6225	|	On Demand	|	6	|		|
|		|	TEC PS Enable	|		|	P1.0	|	11,44	|	0	|	6225	|	On Demand	|	6	|		|
|		|	Purge Switch	|		|	P1.4	|	10,44	|	0	|	6225	|	On Demand	|	7	|	High is flow through MFC; low is through critical orifice.	|
|		|	Laser Interlock	|		|	P1.2	|	43,9	|	0	|	6225	|	On Demand	|	7	|	Input from laser enclosure interlock	|
|		|	Sample pump blocked	|		|	P1.3	|	42,8	|	0	|	6225	|	On Demand	|	7	|	Signal from pressure differential sensor to indicate blocked impactor	|
|		|	Ozone DO	|		|	ctr0	|	37,4	|	0	|	6225	|	On Demand	|	6	|	Output for PWM of ozone generator	|
|		|	Impactor Differential Pressure	|		|	AI0	|	0,8	|	0	|	6225	|	1k	|	7	|	Differential pressure measurement on sample pump.  High value (TBD) indicates that pump is blocked	|
|	CRDS	|	CRDS Blue AI	|		|	AI0	|	68,34	|	0	|	6124	|		|	3	|	Analog input for CRDS blue, dry PMT	|
|		|		|		|	AI1	|	33,66	|	0	|	6124	|		|	3	|	Analog input for CRDS blue, dry , filtered PMT	|
|		|		|		|	AI2	|	65,31	|	0	|	6124	|		|	3	|	Analog input for CRDS blue, high RH PMT	|
|		|		|		|	AI3	|	30,63	|	0	|	6124	|		|	3	|	Analog input for CRDS blue, med RH PMT	|
|		|	CRDS Red AI	|		|	AI0	|	68,34	|	0	|	6132	|		|	5	|	Analog input for CRDS red PMT	|
|		|	CRD Blue Laser Output	|		|	Ctr0	|	2,36	|	0	|	6225	|		|	8	|	Modulation for blue diode	|
|		|	CRD Red Laser Output	|		|	Ctr1	|	40,7	|	0	|	6225	|		|	8	|	Modulation for red diode	|
|		|	PMT Gain	|		|	AO5	|	60,27	|	N/A	|	6704	|		|	6	|		|
|		|		|		|	AO6	|	25,59	|	N/A	|	6704	|		|	6	|		|
|		|		|		|	AO7	|	57,24	|	N/A	|	6704	|		|	6	|		|
|		|		|		|	AO8	|	22,55	|	N/A	|	6704	|		|	6	|		|
|		|		|		|	AO9	|	54,20	|	N/A	|	6704	|		|	6	|		|
|		|	Red Enable	|		|	P0.0	|		|		|	6132	|		|	5	|	Laser enable signal for red laser on CRDS	|
|		|	Blue Enable	|		|	P0.1	|		|	0	|	6124	|		|	3	|	Laser enable signal for blue laser 0 on CRDS	|
|		|		|		|	P0.2	|		|	0	|	6124	|		|	3	|	Laser enable signal for blue laser 1 on CRDS	|
|		|	Red Laser Gain	|		|	AO0	|		|		|	6704	|		|		|		|
|		|	Blue0 Gain	|		|	AO1	|		|		|	6704	|		|		|		|
|		|	Blue1 Gain	|		|	AO2	|		|		|	6704	|		|		|		|
|		|	Purge Switch	|		|	P1.5	|		|		|	6225	|		|		|		|


