---
title: "-CLRSUPPORTLASTERROR (마지막 오류 코드 유지 PInvoke 호출의) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRSUPPORTLASTERROR
dev_langs:
- C++
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e082637e25832c5c5036910f7b67aff53d867bdb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR(PInvoke 호출의 마지막 오류 코드 유지)
**/CLRSUPPORTLASTERROR**, 기본적으로 켜져 있는, 사용 하 여 컴파일한 DLL에 코드에서 네이티브 함수를 호출할 수 있는 P/Invoke 메커니즘을 통해 호출 함수의 마지막 오류 코드는 전처리 **/clr**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}  
```  
  
## <a name="remarks"></a>설명  
 성능이 저하를 의미 마지막 오류 코드를 유지 합니다.  마지막 오류 코드를 유지 하면서의 성능에 영향이 발생 하지 않을 경우 사용 하 여 링크 **/CLRSUPPORTLASTERROR:NO**합니다.  
  
 연결 하 여 성능에 미치는 영향을 최소화할 수 있습니다 **/CLRSUPPORTLASTERROR:SYSTEMDLL**, 저장 하는 함수에 대 한 마지막 오류 코드 시스템 Dll에에서 있습니다.  시스템 DLL은 다음 중 하나로 정의 됩니다.  
  
|||||  
|-|-|-|-|  
|ACLUI 합니다. DLL|ACTIVEDS 합니다. DLL|ADPTIF 합니다. DLL|ADVAPI32 합니다. DLL|  
|ASYCFILT 합니다. DLL|AUTHZ 합니다. DLL|AVICAP32 합니다. DLL|AVIFIL32 합니다. DLL|  
|캐비닛입니다. DLL|CLUSAPI 합니다. DLL|COMCTL32 합니다. DLL|COMDLG32 합니다. DLL|  
|COMSVCS 합니다. DLL|CREDUI 합니다. DLL|CRYPT32 합니다. DLL|CRYPTNET 합니다. DLL|  
|CRYPTUI 합니다. DLL|D3D8THK 합니다. DLL|DBGENG 합니다. DLL|DBGHELP 합니다. DLL|  
|DCIMAN32 합니다. DLL|DNSAPI 합니다. DLL|DSPROP 합니다. DLL|DSUIEXT 합니다. DLL|  
|GDI32 합니다. DLL|GLU32 합니다. DLL|HLINK 합니다. DLL|ICM32 합니다. DLL|  
|IMAGEHLP 합니다. DLL|IMM32 합니다. DLL|IPHLPAPI 합니다. DLL|IPROP 합니다. DLL|  
|KERNEL32 합니다. DLL|KSUSER 합니다. DLL|LOADPERF 합니다. DLL|LZ32 합니다. DLL|  
|MAPI32 합니다. DLL|MGMTAPI 합니다. DLL|고 MOBSYNC 합니다. DLL|MPR 합니다. DLL|  
|MPRAPI 합니다. DLL|MQRT 합니다. DLL|MSACM32 합니다. DLL|MSCMS 합니다. DLL|  
|MSI 합니다. DLL|MSIMG32 합니다. DLL|MSRATING 합니다. DLL|MSTASK 합니다. DLL|  
|MSVFW32 합니다. DLL|MSWSOCK 합니다. DLL|MTXEX 합니다. DLL|NDDEAPI 합니다. DLL|  
|NETAPI32 합니다. DLL|NPPTOOLS 합니다. DLL|NTDSAPI 합니다. DLL|NTDSBCLI 합니다. DLL|  
|NTMSAPI 합니다. DLL|ODBC32 합니다. DLL|ODBCBCP 합니다. DLL|OLE32 합니다. DLL|  
|OLEACC 합니다. DLL|OLEAUT32 합니다. DLL|OLEDLG 합니다. DLL|OPENGL32 합니다. DLL|  
|PDH 합니다. DLL|POWRPROF 합니다. DLL|QOSNAME 합니다. DLL|쿼리입니다. DLL|  
|RASAPI32 합니다. DLL|RASDLG 합니다. DLL|RASSAPI 합니다. DLL|RESUTILS 합니다. DLL|  
|RICHED20 합니다. DLL|RPCNS4 합니다. DLL|RPCRT4 합니다. DLL|RTM 합니다. DLL|  
|RTUTILS 합니다. DLL|SCARDDLG 합니다. DLL|SECUR32 합니다. DLL|SENSAPI 합니다. DLL|  
|SETUPAPI 합니다. DLL|SFC 합니다. DLL|SHELL32 합니다. DLL|SHFOLDER 합니다. DLL|  
|SHLWAPI 합니다. DLL|SISBKUP 합니다. DLL|SNMPAPI 합니다. DLL|SRCLIENT 합니다. DLL|  
|STI 합니다. DLL|TAPI32 합니다. DLL|트래픽이입니다. DLL|URL입니다. DLL|  
|URLMON 합니다. DLL|USER32 합니다. DLL|USERENV 합니다. DLL|USP10 합니다. DLL|  
|UXTHEME 합니다. DLL|VDMDBG 합니다. DLL|버전. DLL|WINFAX 합니다. DLL|  
|WINHTTP 합니다. DLL|WININET 합니다. DLL|WINMM 합니다. DLL|WINSCARD 합니다. DLL|  
|WINTRUST 합니다. DLL|WLDAP32 합니다. DLL|WOW32 합니다. DLL|WS2_32.DLL|  
|WSNMP32 합니다. DLL|WSOCK32.DLL|WTSAPI32 합니다. DLL|XOLEHLP 합니다. DLL|  
  
> [!NOTE]
>  마지막 오류 유지는 동일한 모듈의 CLR 코드에서 사용 하는 관리 되지 않는 함수에 대 한 지원 되지 않습니다.  
  
-   자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  에 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="example"></a>예  
 다음 샘플 마지막 오류를 수정 하는 내보낸 함수를 하나의 네이티브 DLL을 정의 합니다.  
  
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
  
## <a name="example"></a>예  
 다음 샘플에 사용 하는 방법을 보여 주는 DLL 사용 **/CLRSUPPORTLASTERROR**합니다.  
  
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
  
```Output  
GetLastError for application call failed (127).  
GetLastError for system call succeeded (183).  
```  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)