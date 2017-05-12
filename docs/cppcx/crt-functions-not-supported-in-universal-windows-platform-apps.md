---
title: "유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# 유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수
UWP\(유니버설 Windows 플랫폼\) 앱을 빌드할 때는 대부분 CRT\(C 런타임\) 함수를 사용할 수 없습니다. 어떤 경우에는 해결 방법이 제공됩니다. 예를 들어 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 또는 Win32 API를 사용할 수 있습니다. 그러나 지원 API 또는 CRT 함수에 해당하는 기능을 UWP 앱에 적용할 수 없으므로 다른 경우에는 CRT 함수가 금지되었습니다.  
  
 다음 표에서는 UWP 앱을 빌드할 때 사용할 수 없는 CRT 함수를 보여 주고 적용되는 해결 방법을 지정합니다.  
  
## 지원되지 않는 CRT 함수  
  
||||  
|-|-|-|  
|\_beep \_sleep \_seterrormode|이들 함수는 이전 버전 CRT에서 더 이상 사용되지 않습니다. 또한 해당 Win32 API는 UWP 앱에 사용할 수 없습니다.|해결 방법이 없습니다.|  
|chdir \_chdrive getcwd|이들 함수는 더 이상 사용되지 않거나 스레드로부터 안전하지 않습니다.|\_chdir, \_getcwd 및 관련 함수를 사용합니다.|  
|\_cgets \_cgets\_s \_cgetws \_cgetws\_s \_cprintf \_cprintf\_l \_cprintf\_p \_cprintf\_p\_l \_cprintf\_s \_cprintf\_s\_l \_cputs \_cputws \_cscanf \_cscanf\_l \_cscanf\_s \_cscanf\_s\_l \_cwait \_cwprintf \_cwprintf\_l \_cwprintf\_p \_cwprintf\_p\_l \_cwprintf\_s \_cwprintf\_s\_l \_cwscanf \_cwscanf\_l \_cwscanf\_s \_cwscanf\_s\_l \_vcprintf \_vcprintf\_l \_vcprintf\_p \_vcprintf\_p\_l \_vcprintf\_s \_vcprintf\_s\_l \_vcwprintf \_vcwprintf\_l \_vcwprintf\_p \_vcwprintf\_p\_l \_vcwprintf\_s \_vcwprintf\_s\_l \_getch \_getch\_nolock \_getche \_getche\_nolock \_getwch \_getwch\_nolock \_getwche \_getwche\_nolock \_putch \_putch\_nolock \_putwch \_putwch\_nolock \_ungetch \_ungetch\_nolock \_ungetwch \_ungetwch\_nolock \_kbhit kbhit putch cgets cprintf cputs cscanf cwait getch getche ungetch|이들 함수는 콘솔에서 바로 읽고 쓰는 데 사용됩니다. UWP 앱은 GUI 전용이고 콘솔을 지원하지 않습니다.|해결 방법이 없습니다.|  
|getpid|이 함수는 사용되지 않습니다.|\_getpid 또는 Win32 API `GetCurrentProcessId()`를 사용합니다.|  
|\_getdiskfree|사용할 수 없습니다.|Win32 API `GetDiskFreeSpaceExW()`를 사용합니다.|  
|\_getdrive \_getdrives|해당 API는 UWP 앱에 사용할 수 없습니다.|해결 방법이 없습니다.|  
|\_inp \_inpd \_inpw \_outp \_outpd \_outpw inp inpd inpw outp outpd outpw|포트 IO는 UWP 앱에서 지원되지 않습니다.|해결 방법이 없습니다.|  
|\_ismbcalnum \_ismbcalnum\_l \_ismbcalpha \_ismbcalpha\_l \_ismbcdigit \_ismbcdigit\_l \_ismbcgraph \_ismbcgraph\_l \_ismbchira \_ismbchira\_l \_ismbckata \_ismbckata\_l \_ismbcl0 \_ismbcl0\_l \_ismbcl1 \_ismbcl1\_l \_ismbcl2 \_ismbcl2\_l \_ismbclegal \_ismbclegal\_l \_ismbclower \_ismbclower\_l \_ismbcprint \_ismbcprint\_l \_ismbcpunct \_ismbcpunct\_l \_ismbcspace \_ismbcspace\_l \_ismbcsymbol \_ismbcsymbol\_l \_ismbcupper \_ismbcupper\_l \_mbbtombc \_mbbtombc\_l \_mbbtype \_mbbtype\_l \_mbccpy \_mbccpy\_l \_mbccpy\_s \_mbccpy\_s\_l \_mbcjistojms \_mbcjistojms\_l \_mbcjmstojis \_mbcjmstojis\_l \_mbclen \_mbclen\_l \_mbctohira \_mbctohira\_l \_mbctokata \_mbctokata\_l \_mbctolower \_mbctolower\_l \_mbctombb \_mbctombb\_l \_mbctoupper \_mbctoupper\_l \_mbsbtype \_mbsbtype\_l \_mbscat \_mbscat\_l \_mbscat\_s \_mbscat\_s\_l \_mbschr \_mbschr\_l \_mbscmp \_mbscmp\_l \_mbscoll \_mbscoll\_l \_mbscpy \_mbscpy\_l \_mbscpy\_s \_mbscpy\_s\_l \_mbscspn \_mbscspn\_l \_mbsdec \_mbsdec\_l \_mbsicmp \_mbsicmp\_l \_mbsicoll \_mbsicoll\_l \_mbsinc \_mbsinc\_l \_mbslen \_mbslen\_l \_mbslwr \_mbslwr\_l \_mbslwr\_s \_mbslwr\_s\_l \_mbsnbcat \_mbsnbcat\_l \_mbsnbcat\_s \_mbsnbcat\_s\_l \_mbsnbcmp \_mbsnbcmp\_l \_mbsnbcnt \_mbsnbcnt\_l \_mbsnbcoll \_mbsnbcoll\_l \_mbsnbcpy \_mbsnbcpy\_l \_mbsnbcpy\_s \_mbsnbcpy\_s\_l \_mbsnbicmp \_mbsnbicmp\_l \_mbsnbicoll \_mbsnbicoll\_l \_mbsnbset \_mbsnbset\_l \_mbsnbset\_s \_mbsnbset\_s\_l \_mbsncat \_mbsncat\_l \_mbsncat\_s \_mbsncat\_s\_l \_mbsnccnt \_mbsnccnt\_l \_mbsncmp \_mbsncmp\_l \_mbsncoll \_mbsncoll\_l \_mbsncpy \_mbsncpy\_l \_mbsncpy\_s \_mbsncpy\_s\_l \_mbsnextc \_mbsnextc\_l \_mbsnicmp \_mbsnicmp\_l \_mbsnicoll \_mbsnicoll\_l \_mbsninc \_mbsninc\_l \_mbsnlen \_mbsnlen\_l \_mbsnset \_mbsnset\_l \_mbsnset\_s \_mbsnset\_s\_l \_mbspbrk \_mbspbrk\_l \_mbsrchr \_mbsrchr\_l \_mbsrev \_mbsrev\_l \_mbsset \_mbsset\_l \_mbsset\_s \_mbsset\_s\_l \_mbsspn \_mbsspn\_l \_mbsspnp \_mbsspnp\_l \_mbsstr \_mbsstr\_l \_mbstok \_mbstok\_l \_mbstok\_s \_mbstok\_s\_l \_mbsupr \_mbsupr\_l \_mbsupr\_s \_mbsupr\_s\_l is\_wctype|멀티바이트 문자열은 UWP 앱에서 지원되지 않습니다.|대신 유니코드 문자열을 사용합니다.|  
|\_pclose \_pipe \_popen \_wpopen|파이프 기능은 UWP 앱에 사용할 수 없습니다.|해결 방법이 없습니다.|  
|\_resetstkoflw|지원 Win32 API는 UWP 앱에 사용할 수 없습니다.|해결 방법이 없습니다.|  
|\_getsystime \_setsystime|이들 API는 이전 CRT 버전에서 더 이상 사용되지 않습니다. 또한 사용자는 권한이 없으므로 UWP 앱에서 시스템 시간을 설정할 수 없습니다.|시스템 시간만 가져오려면 Win32 API `GetSystemTime`을 사용합니다. 시스템 시간을 설정할 수 없습니다.|  
|\_environ \_putenv \_putenv\_s \_searchenv \_searchenv\_s \_dupenv\_s \_wputenv \_wputenv\_s \_wsearchenv getenv getenv\_s putenv \_wdupenv\_s \_wenviron \_wgetenv \_wgetenv\_s \_wsearchenv\_s tzset|환경 변수는 UWP 앱에 사용할 수 없습니다.|해결 방법이 없습니다. 표준 시간대를 설정하려면 \_tzset를 사용합니다.|  
|\_loaddll \_getdllprocaddr \_unloaddll|이들 함수는 이전 CRT 버전에서 더 이상 사용되지 않습니다. 또한 사용자는 같은 응용 프로그램 패키지의 DLL에서만 DLL을 로드할 수 있습니다.|Win32 API `LoadPackagedLibrary`, `GetProcAddress` 및 `FreeLibrary`를 사용하여 패키지된 DLL을 로드 및 사용합니다.|  
|\_wexecl \_wexecle \_wexeclp \_wexeclpe \_wexecv \_wexecve \_wexecvp \_wexecvpe \_execl \_execle \_execlp \_execlpe \_execv \_execve \_execvp \_execvpe \_spawnl \_spawnle \_spawnlp \_spawnlpe \_spawnv \_spawnve \_spawnvp \_spawnvpe \_wspawnl \_wspawnle \_wspawnlp \_wspawnlpe \_wspawnv \_wspawnve \_wspawnvp \_wspawnvpe \_wsystem execl execle execlp execlpe execv execve execvp execvpe spawnl spawnle spawnlp spawnlpe spawnv spawnve spawnvp spawnvpe system|이 기능은 UWP 앱에서 사용할 수 없습니다. UWP 앱은 다른 UWP 앱이나 데스크톱 앱을 호출할 수 없습니다.|해결 방법이 없습니다.|  
|\_heapwalk \_heapadd \_heapchk \_heapset \_heapused|일반적으로 이들 기능은 힙 작업을 하는 데 사용됩니다. 그러나 해당 Win32 API는 UWP 앱에서 지원되지 않습니다. 또한 앱에서 더 이상 전용 힙을 만들거나 사용할 수 없습니다.|해결 방법이 없습니다. 그러나 `_heapwalk`는 DEBUG CRT에서 디버깅 목적으로만 사용할 수 있습니다. Windows 스토어에 업로드되는 앱에서는 사용할 수 없습니다.|  
  
 다음 함수는 UWP 앱용 CRT에서 사용할 수 있지만 해당 Win32 또는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] API를 사용할 수 없는 경우\(예: 큰 코드베이스를 이식하는 경우\)에만 사용해야 합니다.  
  
|||  
|-|-|  
|단일 바이트 문자열 함수 \- 예: `strcat`, `strcpy`, `strlwr` 등.|모든 Win32 API 및 노출되는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] API는 유니코드 문자 집합만 사용하므로 UWP 앱을 엄격히 유니코드로 설정합니다. 단일 바이트 함수는 큰 코드베이스 이식용으로 남아 있지만 사용을 피해야 하고 가능하면 대신 해당 전각 문자 함수를 사용해야 합니다.|  
|스트림 IO 및 하위 수준 파일 IO 함수 \- 예: `fopen`, `open` 등.|이들 함수는 동기화되는데 UWP 앱에서는 동기화가 권장되지 않습니다. UWP 앱에서는 UI 스레드 잠금을 방지하기 위해 비동기 API를 사용하여 파일을 열고, 읽고, 씁니다. 해당 API의 예제는 `Windows::Storage::FileIO` 클래스의 예제입니다.|  
  
## Windows 8.x 스토어 앱 및 Windows Phone 8.x 앱  
 이전에 설명한 API 이외에 다음 API는 Windows 8.x 스토어 앱 및 Windows Phone 8.x 앱에서 사용할 수 없습니다.  
  
||||  
|-|-|-|  
|\_beginthread \_beginthreadex \_endthread \_endthreadex|스레딩 Win32 API는 Windows 8.x 스토어 앱에서 사용할 수 없습니다.|대신 `Windows Runtime Windows::System::Threading::ThreadPool` 또는 `concurrency::task`를 사용합니다.|  
|\_chdir \_wchdir \_getcwd \_getdcwd \_wgetcwd \_wgetdcwd|작업 디렉터리 개념은 Windows 8.x 스토어 앱에 적용되지 않습니다.|대신 전체 경로를 사용합니다.|  
|\_getpid|이 함수는 이전 버전 CRT에서 더 이상 사용되지 않습니다.|Win32 API `GetCurrentProcessId()`를 사용합니다.|  
|\_isleadbyte\_l \_ismbbalnum, \_ismbbalnum\_l, \_ismbbalpha, \_ismbbalpha \_ismbbalpha\_l \_ismbbgraph \_ismbbgraph\_l \_ismbbkalnum \_ismbbkalnum\_l \_ismbbkana \_ismbbkana\_l \_ismbbkprint \_ismbbkprint\_l \_ismbbkpunct \_ismbbkpunct\_l \_ismbblead \_ismbblead\_l \_ismbbprint \_ismbbprint\_l \_ismbbpunct \_ismbbpunct\_l \_ismbbtrail \_ismbbtrail\_l \_ismbslead \_ismbslead\_l \_ismbstrail \_ismbstrail\_l \_mbsdup isleadbyte|멀티바이트 문자열은 Windows 8.x 스토어 앱에서 지원되지 않습니다.|대신 유니코드 문자열을 사용합니다.|  
|\_tzset|환경 변수는 Windows 8.x 스토어 앱에 사용할 수 없습니다.|해결 방법이 없습니다.|  
|\_get\_heap\_handle, \_heapmin|해당 Win32 API는 Windows 8.x 스토어 앱에서 지원되지 않습니다. 또한 앱에서 더 이상 전용 힙을 만들 수 없습니다.|해결 방법이 없습니다. 그러나 `_get_heap_handle`은 DEBUG CRT에서 디버깅 목적으로만 사용할 수 있습니다.|