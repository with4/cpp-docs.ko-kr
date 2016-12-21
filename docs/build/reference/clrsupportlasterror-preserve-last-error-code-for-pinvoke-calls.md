---
title: "/CLRSUPPORTLASTERROR(PInvoke 호출의 마지막 오류 코드 유지) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRSUPPORTLASTERROR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRSUPPORTLASTERROR 링커 옵션"
  - "-CLRSUPPORTLASTERROR 링커 옵션"
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /CLRSUPPORTLASTERROR(PInvoke 호출의 마지막 오류 코드 유지)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본적으로 활성화되어 있는 **\/CLRSUPPORTLASTERROR**를 사용하면 P\/Invoke 메커니즘을 통해 호출한 함수의 마지막 오류 코드를 저장할 수 있습니다. 이렇게 하면 **\/clr**를 사용하여 컴파일한 코드에서 DLL의 네이티브 함수를 호출할 수 있습니다.  
  
## 구문  
  
```  
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}  
```  
  
## 설명  
 마지막 오류 코드를 저장하면 성능이 저하될 수 있습니다.  마지막 오류 코드를 저장하는 데 따른 성능 저하를 방지하려면 **\/CLRSUPPORTLASTERROR:NO**를 사용하여 링크합니다.  
  
 시스템 DLL의 함수에 대한 마지막 오류 코드만 저장하는 **\/CLRSUPPORTLASTERROR:SYSTEMDLL**을 사용하여 링크하면 성능에 미치는 영향을 최소화할 수 있습니다.  시스템 DLL은 다음 중 하나로 정의됩니다.  
  
|||||  
|-|-|-|-|  
|ACLUI.DLL|ACTIVEDS.DLL|ADPTIF.DLL|ADVAPI32.DLL|  
|ASYCFILT.DLL|AUTHZ.DLL|AVICAP32.DLL|AVIFIL32.DLL|  
|CABINET.DLL|CLUSAPI.DLL|COMCTL32.DLL|COMDLG32.DLL|  
|COMSVCS.DLL|CREDUI.DLL|CRYPT32.DLL|CRYPTNET.DLL|  
|CRYPTUI.DLL|D3D8THK.DLL|DBGENG.DLL|DBGHELP.DLL|  
|DCIMAN32.DLL|DNSAPI.DLL|DSPROP.DLL|DSUIEXT.DLL|  
|GDI32.DLL|GLU32.DLL|HLINK.DLL|ICM32.DLL|  
|IMAGEHLP.DLL|IMM32.DLL|IPHLPAPI.DLL|IPROP.DLL|  
|KERNEL32.DLL|KSUSER.DLL|LOADPERF.DLL|LZ32.DLL|  
|MAPI32.DLL|MGMTAPI.DLL|MOBSYNC.DLL|MPR.DLL|  
|MPRAPI.DLL|MQRT.DLL|MSACM32.DLL|MSCMS.DLL|  
|MSI.DLL|MSIMG32.DLL|MSRATING.DLL|MSTASK.DLL|  
|MSVFW32.DLL|MSWSOCK.DLL|MTXEX.DLL|NDDEAPI.DLL|  
|NETAPI32.DLL|NPPTOOLS.DLL|NTDSAPI.DLL|NTDSBCLI.DLL|  
|NTMSAPI.DLL|ODBC32.DLL|ODBCBCP.DLL|OLE32.DLL|  
|OLEACC.DLL|OLEAUT32.DLL|OLEDLG.DLL|OPENGL32.DLL|  
|PDH.DLL|POWRPROF.DLL|QOSNAME.DLL|QUERY.DLL|  
|RASAPI32.DLL|RASDLG.DLL|RASSAPI.DLL|RESUTILS.DLL|  
|RICHED20.DLL|RPCNS4.DLL|RPCRT4.DLL|RTM.DLL|  
|RTUTILS.DLL|SCARDDLG.DLL|SECUR32.DLL|SENSAPI.DLL|  
|SETUPAPI.DLL|SFC.DLL|SHELL32.DLL|SHFOLDER.DLL|  
|SHLWAPI.DLL|SISBKUP.DLL|SNMPAPI.DLL|SRCLIENT.DLL|  
|STI.DLL|TAPI32.DLL|TRAFFIC.DLL|URL.DLL|  
|URLMON.DLL|USER32.DLL|USERENV.DLL|USP10.DLL|  
|UXTHEME.DLL|VDMDBG.DLL|VERSION.DLL|WINFAX.DLL|  
|WINHTTP.DLL|WININET.DLL|WINMM.DLL|WINSCARD.DLL|  
|WINTRUST.DLL|WLDAP32.DLL|WOW32.DLL|WS2\_32.DLL|  
|WSNMP32.DLL|WSOCK32.DLL|WTSAPI32.DLL|XOLEHLP.DLL|  
  
> [!NOTE]
>  동일한 모듈에서 CLR 코드에 사용되는 관리되지 않는 함수에 대해서는 마지막 오류를 저장할 수 없습니다.  
  
-   자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 마지막 오류를 수정하는 내보낸 함수 하나와 함께 네이티브 DLL을 정의합니다.  
  
```  
// CLRSUPPORTLASTERROR_dll.cpp  
// compile with: /LD  
#include <windows.h>  
#include <math.h>  
  
#pragma unmanaged  
__declspec(dllexport) double MySqrt(__int64 n) {  
   SetLastError(DWORD(-1));  
   return sqrt(double(n));  
}  
```  
  
## 예제  
 다음 샘플에서는 DLL을 사용하여 **\/CLRSUPPORTLASTERROR**를 적용하는 방법을 보여 줍니다.  
  
```  
// CLRSUPPORTLASTERROR_client.cpp  
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll  
// processor: x86  
#include <windows.h>  
#include <wininet.h>  
#include <stdio.h>  
#include <math.h>  
  
#pragma comment(lib, "wininet.lib")  
  
double MySqrt(__int64 n);  
  
#pragma managed  
int main() {  
   double   d = 0.0;  
   __int64 n = 65;  
   HANDLE  hGroup = NULL;  
   GROUPID groupID;  
   DWORD   dwSet = 127, dwGet = 37;  
  
   SetLastError(dwSet);  
   d = MySqrt(n);  
   dwGet = GetLastError();  
  
   if (dwGet == DWORD(-1))  
      printf_s("GetLastError for application call succeeded (%d).\n",  
             dwGet);  
   else  
      printf_s("GetLastError for application call failed (%d).\n",  
             dwGet);  
  
   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,  
                           0, 0, &groupID, 0);  
   dwGet = GetLastError();  
   if (dwGet == 183)  
      printf_s("GetLastError for system call succeeded (%d).\n",  
             dwGet);  
   else  
      printf_s("GetLastError for system call failed (%d).\n",  
             dwGet);  
}  
```  
  
  **GetLastError \(127\)의 응용 프로그램 호출에 실패했습니다.**   
**GetLastError \(183\)의 시스템 호출에 성공했습니다.**   
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)