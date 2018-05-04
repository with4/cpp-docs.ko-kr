---
title: MFC DLL에 대 한 질문과 대답 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f5740989562aea799f3a49adfa464e2c460acb3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="dll-frequently-asked-questions"></a>DLL 관련 질문과 대답  
  
다음은 몇 가지 질문과 대답 (FAQ) Dll에 대 한입니다.  
    
-   [MFC DLL은 여러 스레드를 만들 수 있습니까?](#mfc_multithreaded_1)  

-   [다중 스레드 응용 프로그램에 서로 다른 여러 스레드에서 MFC DLL에 액세스할 수 있습니까?](#mfc_multithreaded_2)  
  
-   [있습니까? 모든 MFC 클래스 또는 MFC DLL에서 사용할 수 없는 함수](#mfc_prohibited_classes)  
  
-   [로드 시 클라이언트 응용 프로그램의 성능을 향상 시키려면 어떤 최적화 기술을 사용 해야 합니까?](#mfc_optimization)  
  
-   [일반 MFC DLL 내에서 메모리 누수 있지만 코드 제대로 보이는 합니다. 메모리 누수를 찾으려면 어떻게 해야 합니까?](#memory_leak)  

## <a name="mfc_multithreaded_1"></a> MFC DLL은 여러 스레드를 만들 수 있습니까?  
  
초기화 하는 동안 MFC DLL 안전 하 게 만들 수 다중 스레드 Win32 스레드 로컬 저장소 (TLS)와 같은 함수를 사용으로 제외 하 고 **TlsAlloc** 스레드 로컬 저장소를 할당 합니다. 그러나 MFC DLL을 사용 하는 경우 **__declspec (thread)** 스레드 로컬 저장소를 할당 하려면 클라이언트 응용 프로그램 해야 수 암시적으로 DLL에 연결 합니다. 클라이언트 응용 프로그램 DLL에 대 한 호출에 명시적으로 연결 하는 경우 **LoadLibrary** DLL을 성공적으로 로드 되지 것입니다. 여러 스레드에서 MFC Dll 내 만들기에 대 한 자세한 내용은 기술 자료 문서 "PRB:: 호출 LoadLibrary()를 부하는 DLL을가 정적 TLS" (Q118816)을 참조 하십시오. 스레드 로컬 변수 Dll에 대 한 자세한 내용은 참조 하십시오. [스레드](../cpp/thread.md)합니다.
  
 MFC DLL 시작 시 새 MFC 스레드를 만드는 응용 프로그램에 의해 로드 되 면 응답 중지 됩니다. 여기에 호출 하 여 스레드를 만들 때마다 `AfxBeginThread` 또는 `CWinThread::CreateThread` 내부:  
  
-   `InitInstance` 의 `CWinApp`-파생 된 기본 MFC DLL에는 개체입니다.  
  
-   제공 된 `DllMain` 또는 **RawDllMain** MFC 기본 DLL의 함수입니다.  
  
-   제공 된 `DllMain` 또는 **RawDllMain** MFC 확장 DLL의에서 함수입니다.  
  
 초기화 하는 동안 스레드를 생성 하는 방법에 대 한 자세한 내용은 기술 자료 문서 "PRB:: 없습니다 만들는 MFC 스레드 중 DLL 시작" (Q142243)을 참조 하십시오.  
  
## <a name="mfc_multithreaded_2"></a> 다중 스레드 응용 프로그램에 서로 다른 여러 스레드에서 MFC DLL에 액세스할 수 있습니까?
다중 스레드 응용 프로그램에는 서로 다른 여러 스레드에서 MFC에 동적으로 연결 되는 기본 MFC Dll과 MFC 확장 Dll 액세스할 수 있습니다. 및 Visual c + + 버전 4.2부터 응용 프로그램에 응용 프로그램에서 만들어진 여러 스레드에서 MFC에 정적으로 링크는 기본 MFC Dll에 액세스할 수 있습니다.  
  
 버전 4.2 이전 하나의 외부 스레드 정적으로 MFC에 링크 하는 MFC 기본 DLL에 연결할 수 없습니다. Visual c + + 버전 4.2) (이전 여러 스레드에서 MFC에 정적으로 링크 되는 기본 MFC Dll에 액세스 하는 제한에 대 한 자세한 내용은 기술 자료 문서를 참조 하십시오. "여러 스레드 및 MFC 동적으로 링크할 수" (Q122676).  
  
 용어 USRDLL Visual c + + 설명서에 더 이상 사용 되는 참고 합니다. 정적으로 MFC에 링크 하는 MFC 기본 DLL은 이전 USRDLL와 동일한 특성입니다.  


## <a name="mfc_prohibited_classes"></a> 있습니까? 모든 MFC 클래스 또는 MFC DLL에서 사용할 수 없는 함수
확장 Dll 사용의 `CWinApp`-클라이언트 응용 프로그램의 클래스를 파생 합니다. 가질 수 없습니다 자신의 `CWinApp`-클래스를 파생 합니다.  
  
일반 MFC Dll 있어야는 `CWinApp`-파생 된 클래스 및 해당 응용 프로그램 클래스의 단일 개체는 MFC 응용 프로그램과 마찬가지로 합니다. 와 달리는 `CWinApp` 응용 프로그램의 개체는 `CWinApp` DLL의 개체는 기본 메시지 펌프가 없습니다.  
  
 되므로 `CWinApp::Run` 기본 메시지 펌프를 소유 하는 응용 프로그램에 메커니즘 DLL에 적용 되지 않습니다. 응용 프로그램의 기본 메시지 펌프 호출 하는 DLL에서 내보낸 루틴을 호출 해야 경우 DLL 모덜리스 대화 상자은 별도의 주 프레임 창는 `CWinApp::PreTranslateMessage` DLL의 응용 프로그램 개체의 멤버 함수입니다.  

## <a name="mfc_optimization"></a> 어떤 최적화 기술을 클라이언트 응용 프로그램을 개선 하기 위해 사용 해야 합니까&#39;로드할 때 s 성능?
DLL에 정적으로 변경 하는 일반적인 MFC에 링크 하는 MFC 기본 DLL은 동적으로 MFC에 링크를 MFC DLL 파일 크기를 줄입니다.  
  
 DLL에 많은 수의 내보낸된 함수 경우는 함수를 내보내려면.def 파일 사용 (사용 하는 대신 **__declspec (dllexport)**).def 파일을 사용 하 여 [NONAME 특성](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) 내보낸 함수를 각 합니다. NONAME 특성 파일 크기를 줄이는 DLL의 내보내기 테이블에 저장 될 함수 이름이 아닌 서 수 값만 하면 됩니다.  
  
 응용 프로그램이 로드 될 때 암시적으로 응용 프로그램에 연결 된 Dll 로드 됩니다. 로드할 때의 성능 향상을 위해 서로 다른 Dll로 나누는 해 보십시오. 즉 하나의 DLL에 로드 후 즉시 호출 응용 프로그램에서 필요로 하는 모든 함수 및 호출 응용 프로그램을 암시적으로 해당 DLL에 연결 합니다. 다른 함수에 호출 응용 프로그램 바로 필요 하지 않은 다른 DLL에 포함 시키고 응용 프로그램이 명시적으로 링크 해당 DLL에 있습니다. 자세한 내용은 참조 [사용 하려면 사용할 링크 방법 결정](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)합니다.  

## <a name="memory_leak"></a> 있습니다&#39;s 내 기본 MFC DLL 하지만 코드에서 메모리 누수에 결함이 있습니다. 메모리 누수를 찾으려면 어떻게 해야 합니까?  
  
한 가지 가능한 원인은 메모리 누수는 MFC 메시지 처리기 함수 내에서 사용 되는 임시 개체를 만듭니다. MFC 응용 프로그램에서 이러한 임시 개체는 자동으로 정리에 `CWinApp::OnIdle()` 메시지를 처리 하는 사이에서 호출 함수입니다. 그러나 MFC 동적 연결 라이브러리 (Dll)에 `OnIdle()` 함수 자동으로 호출 되지 않습니다. 결과적으로, 임시 개체 하지 자동으로 정리 됩니다. 명시적으로 호출 해야 DLL 임시 개체를 정리 하려면 `OnIdle(1)` 주기적으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)