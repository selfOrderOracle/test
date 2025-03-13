Category	Quality Scenario (QS)	SCB-LF (Circular, Lock-Free)	MQ-Mutex (Multi-Queue, Mutex-Based)	LB-Mutex (Linear Buffer, Mutex-Based)	Best Choice
Usability	QS_3 Translation Accuracy	✅ High - Predictable frame order	⚠️ Medium - Mutex contention may cause dropped frames	⚠️ Medium - Linear buffer can lead to latency in high loads	SCB-LF
Performance	QS_2 End-to-End Performance	✅ High - Non-blocking, low latency	⚠️ Medium - Mutex locks add delay	⚠️ Low - Linear buffer needs constant resizing or overflow handling	SCB-LF
Performance	QS_9 Resource Efficiency (for TV)	✅ High - Memory-efficient	⚠️ Medium - Needs more memory for queues	⚠️ Low - Inefficient for streaming data, frequent reallocations	SCB-LF
Availability	QS_8 System Fault Tolerance	✅ High - No deadlocks or resource starvation	⚠️ Medium - Risk of deadlocks	⚠️ Low - Memory overflow or reallocation failures possible	SCB-LF
Performance	QS_1 Preprocessing Performance	✅ High - Real-time processing	⚠️ Medium - Mutexes introduce delay	⚠️ Low - Linear processing delays under heavy load	SCB-LF
Usability	QS_4 Visual Realism & Naturalness	✅ High - Smooth frame sequencing without jitter	⚠️ Medium - Mutex locks cause occasional frame jitter	⚠️ Medium - Frames might stutter due to buffer resizing	SCB-LF
Modifiability	QS_6 Support Multiple Languages	⚠️ Medium - Optimized for performance but harder to modify	✅ High - Easier to extend for multiple languages	✅ High - Linear buffer can be modified but at performance cost	MQ-Mutex / LB-Mutex
