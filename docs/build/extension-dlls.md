---
title: "확장 DLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afxdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL 라이브러리"
  - "DLL[C++], 확장"
  - "확장 DLL[C++]"
  - "확장 DLL[C++], 확장 DLL 정보"
  - "메모리[C++], DLL"
  - "MFC DLL[C++], 확장 DLL"
  - "MFC 확장 DLL[C++]"
  - "리소스 공유[C++]"
  - "공유 DLL 버전[C++]"
  - "공유 리소스[C++]"
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 확장 DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 확장 DLL은 일반적으로 기존의 MFC 라이브러리 클래스에서 파생된 다시 사용할 수 있는 클래스를 구현하는 DLL입니다.  
  
 MFC 확장 DLL에는 다음과 같은 기능 및 요구 사항이 있습니다.  
  
-   클라이언트 실행 파일은 **\_AFXDLL**이 정의된 상태에서 컴파일된 MFC 응용 프로그램이어야 합니다.  
  
-   동적으로 MFC에 링크한 기본 DLL에서 확장 DLL을 사용할 수도 있습니다.  
  
-   확장 DLL은 `_AFXEXT`가 정의된 상태에서 컴파일되어야 합니다.  그러면 **\_AFXDLL**도 정의되고 MFC 헤더 파일에서 올바른 선언을 가져올 수 있습니다.  또한 DLL을 빌드할 때 **AFX\_EXT\_CLASS**가 **\_\_declspec\(dllexport\)**으로 정의될 수 있으며, 이러한 정의는 이 매크로를 사용하여 확장 DLL에 클래스를 선언할 경우에 반드시 필요합니다.  
  
-   확장 DLL은 `CWinApp`에서 파생된 클래스를 인스턴스화하지 않아야 하며, 클라이언트 응용 프로그램 또는 DLL의 도움을 받아 이 개체를 제공해야 합니다.  
  
-   그러나 확장 DLL은 `DllMain` 함수를 제공해야 하며 이 함수에서 필요한 초기화 작업을 수행해야 합니다.  
  
 확장 DLL은 MFC의 공유 버전이라고도 하는 MFC의 동적 연결 라이브러리 버전을 사용하여 빌드됩니다.  MFC의 공유 버전을 사용하여 빌드된 MFC 실행 파일\(응용 프로그램 또는 기본 DLL\)만 확장 DLL을 사용할 수 있습니다.  클라이언트 응용 프로그램과 확장 DLL은 모두 같은 버전의 MFCx0.dll을 사용해야 합니다.  확장 DLL을 사용하면 MFC에서 새로운 사용자 지정 클래스를 파생시킨 다음 DLL을 호출하는 응용 프로그램에 이 확장된 버전의 MFC를 제공할 수 있습니다.  
  
 확장 DLL은 응용 프로그램과 DLL 간에 MFC 파생 개체를 전달하는 데에도 사용할 수 있습니다.  전달된 개체와 연관된 멤버 함수는 개체가 작성되었던 모듈 안에 있습니다.  MFC의 공유 DLL 버전을 사용하면 이 함수들을 정확하게 내보내므로 응용 프로그램과 이를 로드한 확장 DLL 간에 MFC 또는 MFC 파생 개체 포인터를 자유롭게 전달할 수 있습니다.  
  
 MFC 확장 DLL은 응용 프로그램이 MFC의 공유 DLL 버전을 사용할 때와 같은 방법으로 MFC의 공유 버전을 사용합니다. 이 때 다음과 같은 추가 고려 사항이 있습니다.  
  
-   MFC 확장 DLL은 `CWinApp` 파생 개체를 포함하지 않으며  클라이언트 응용 프로그램의 `CWinApp` 파생 개체를 사용해야 합니다.  즉, 클라이언트 응용 프로그램에서 기본 메시지 펌프, 유휴 루프 등을 갖습니다.  
  
-   MFC 확장 DLL은 해당 `DllMain` 함수에서 `AfxInitExtensionModule`을 호출합니다.  이 함수의 반환 값을 확인하여  `AfxInitExtensionModule`의 반환 값이 0이면 `DllMain` 함수에서 0을 반환해야 합니다.  
  
-   MFC 확장 DLL에서 응용 프로그램에 `CRuntimeClass` 개체 또는 리소스를 내보내도록 하려면 초기화 시 **CDynLinkLibrary** 개체를 만듭니다.  
  
 MFC 버전 4.0 이전에는 이러한 형식의 DLL을 AFXDLL이라고 했습니다.  AFXDLL은 DLL을 빌드할 때 정의되는 전처리기 기호 **\_AFXDLL**을 나타냅니다.  
  
 MFC의 공유 버전에 대한 가져오기 라이브러리는 [MFC DLL의 명명 규칙](../build/naming-conventions-for-mfc-dlls.md)에 설명된 규칙에 따라 이름이 지정됩니다.  Visual C\+\+에서는 미리 빌드된 MFC DLL 버전과, 응용 프로그램과 함께 사용 및 배포할 수 있는 여러 개의 비 MFC DLL을 함께 제공합니다.  이들은 Program Files\\Microsoft Visual Studio 폴더에 설치되는 Redist.txt에 문서화되어 있습니다.  
  
 .def 파일을 사용하여 내보내는 경우에는 헤더 파일의 처음과 끝 부분에 다음 코드를 추가합니다.  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 이 네 줄의 코드를 추가하면 전체 코드가 확장 DLL에 대해 올바르게 컴파일됩니다.  이 네 줄의 코드가 없으면 DLL이 제대로 컴파일 또는 링크되지 않을 수 있습니다.  
  
 MFC 또는 MFC 파생 개체 포인터를 MFC DLL에 전달하거나 MFC DLL로부터 전달받아야 하는 경우에는 해당 DLL이 확장 DLL이어야 합니다.  전달된 개체와 연관된 멤버 함수는 개체가 작성되었던 모듈 안에 있습니다.  MFC의 공유 DLL 버전을 사용하면 이 함수들을 정확하게 내보내므로 응용 프로그램과 이를 로드한 확장 DLL 간에 MFC 또는 MFC 파생 개체 포인터를 자유롭게 전달할 수 있습니다.  
  
 C\+\+ 이름 관리 및 내보내기 문제로 인해, 플랫폼이 다른 경우에는 같은 DLL의 디버그 버전과 일반 정품 버전 간에 확장 DLL의 내보내기 목록이 서로 다를 수 있습니다.  일반 정품 버전의 MFCx0.dll에는 약 2,000개의 내보내는 진입점이 있으며, 디버그 버전의 MFCx0D.dll에는 약 3,000개의 내보내는 진입점이 있습니다.  
  
## 메모리 관리  
 클라이언트 응용 프로그램의 주소 공간에 로드되는 MFCx0.dll과 모든 확장 DLL은 동일한 응용 프로그램에 있는 것처럼 동일한 메모리 할당자, 리소스 로딩 및 기타 MFC 전역 상태를 사용합니다.  이는 비 MFC DLL 라이브러리와 기본 DLL이 정반대의 작업을 수행하며 각 DLL이 자체의 메모리 풀에서 할당하도록 하므로 중요한 사항입니다.  
  
 확장 DLL이 메모리를 할당하면 해당 메모리는 다른 응용 프로그램에서 할당된 개체와 자유롭게 혼합될 수 있습니다.  또한 동적으로 MFC에 링크하는 응용 프로그램에 문제가 발생하는 경우 운영 체제의 보호 기능은 해당 DLL을 공유하는 다른 MFC 응용 프로그램의 무결성이 유지되도록 합니다.  
  
 마찬가지로, 다른 전역 MFC 상태는 리소스를 로드해오는 현재 실행 파일처럼 클라이언트 응용 프로그램과 모든 MFC 확장 DLL 및 MFCx0.dll 자체 간에 공유됩니다.  
  
## 리소스 및 클래스 공유  
 리소스 내보내기는 리소스 목록을 통해 수행됩니다.  각 응용 프로그램에는 **CDynLinkLibrary** 개체의 단일 연결 리스트가 포함되어 있습니다.  리소스를 찾을 때 리소스를 로드하는 대부분의 표준 MFC 구현에서는 현재 리소스 모듈\(`AfxGetResourceHandle`\)을 먼저 확인하고, 현재 리소스 모듈에서 리소스를 찾지 못하면 **CDynLinkLibrary** 개체의 목록으로 이동하여 요청한 리소스를 로드하려고 시도합니다.  
  
 이 목록으로 이동하는 경우에는 리소스를 찾는 속도가 다소 느려지고 리소스 ID 범위를 관리해야 한다는 단점이 있습니다.  한편, 여러 확장 DLL에 연결되는 클라이언트 응용 프로그램에서 DLL 인스턴스 핸들을 지정하지 않고도 DLL에서 제공하는 임의의 리소스를 사용할 수 있다는 장점도 있습니다.  `AfxFindResourceHandle`은 지정된 일치 항목을 조회하기 위해 리소스 목록을 살펴보는 데 사용되는 API입니다.  이 API는 리소스의 이름 및 형식을 받아서 해당 리소스가 처음 발견된 리소스 핸들 또는 NULL을 반환합니다.  
  
 리소스 목록으로 이동하지 않고 지정한 장소에서만 리소스를 로드하려면 `AfxGetResourceHandle` 및 `AfxSetResourceHandle` 함수를 사용하여 기존 핸들을 저장하고 새로운 핸들을 설정합니다.  기존의 리소스 핸들은 클라이언트 응용 프로그램에 반환되기 전에 복원되어야 합니다.  이러한 방법을 사용하여 메뉴를 명시적으로 로드하는 것에 대한 예제를 보려면 MFC 샘플 [DLLHUSK](http://msdn.microsoft.com/ko-kr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90)에 있는 Testdll2.cpp를 참조하십시오.  
  
 MFC 이름이 지정된 MFC 개체의 동적 생성도 이와 유사합니다.  MFC 개체의 deserialization 메커니즘에서는 모든 `CRuntimeClass` 개체를 등록하여 요청된 형식의 C\+\+ 개체를 저장된 순서에 따라 동적으로 생성하는 방법으로 다시 생성할 수 있어야 합니다.  
  
 MFC 샘플 [DLLHUSK](http://msdn.microsoft.com/ko-kr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90)의 경우, 이 목록의 형식은 다음과 같습니다.  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
               |                      |  
          TESTDLL2.DLL           TESTDLL2.DLL  
               |                      |  
          TESTDLL1.DLL           TESTDLL1.DLL  
               |                      |  
           MFCOxxD.DLL                |  
               |                      |  
           MFCDxxD.DLL                |  
               |                      |  
            MFCxxD.DLL            MFCxx.DLL  
```  
  
 여기서 *xx*는 버전 번호입니다. 예를 들어, 42는 버전 4.2를 나타냅니다.  
  
 MFCxx.dll은 대개 리소스 및 클래스 목록의 마지막에 있습니다.  MFCxx.dll에는 모든 표준 명령 ID에 대한 프롬프트 문자열을 비롯하여 표준 MFC 리소스가 모두 포함되어 있습니다.  이 DLL을 목록의 끝에 두면 DLL 및 클라이언트 응용 프로그램은 표준 MFC 리소스의 자체 복사본을 갖는 대신 MFCxx.dll의 공유 리소스에 의존하게 됩니다.  
  
 모든 DLL의 리소스 및 클래스 이름을 클라이언트 응용 프로그램의 네임스페이스에 병합하면 사용자가 ID 또는 이름을 선택할 때 주의해야 한다는 단점이 있습니다.  
  
 [DLLHUSK](http://msdn.microsoft.com/ko-kr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) 샘플에서는 여러 개의 헤더 파일을 사용하여 공유 리소스의 네임스페이스를 관리합니다.  
  
 MFC 확장 DLL이 각 응용 프로그램에 대한 추가 데이터를 관리해야 하는 경우에는 **CDynLinkLibrary**에서 새 클래스를 파생시켜 `DllMain`에서 이 클래스를 만들 수 있습니다.  이 경우 해당 DLL은 실행 시 현재 응용 프로그램의 **CDynLinkLibrary** 개체 목록을 확인하여 해당 확장 DLL에 맞는 개체를 찾습니다.  
  
### 수행할 작업  
  
-   [확장 DLL 초기화](../build/initializing-extension-dlls.md)  
  
### 추가 정보  
  
-   [공유 리소스 파일 사용 팁](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
  
-   [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)  
  
-   [정적으로 MFC에 링크된 기본 DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [기본 DLL에서 데이터베이스, OLE 및 소켓 확장 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)