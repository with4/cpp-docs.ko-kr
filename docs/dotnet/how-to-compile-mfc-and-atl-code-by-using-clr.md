---
title: 방법:-clr을 사용 하 여 MFC 및 ATL 코드 컴파일 | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], interoperability
- ATL [C++], interoperability
- mixed assemblies [C++], MFC code
- mixed assemblies [C++], ATL code
- /clr compiler option [C++], compiling ATL and MFC code
- interoperability [C++], /clr compiler option
- regular MFC DLLs [C++], /clr compiler option
- interop [C++], /clr compiler option
- extension DLLs [C++], /clr compiler option
ms.assetid: 12464bec-33a4-482c-880a-c078de7f6ea5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7412d69230bcb6375a042d6cf8e8f27a3d9eac9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136069"
---
# <a name="how-to-compile-mfc-and-atl-code-by-using-clr"></a>방법: /clr을 사용하여 MFC 및 ATL 코드 컴파일
이 항목에서는 기존 MFC 및 ATL 프로그램을 공용 언어 런타임을 대상으로 컴파일하는 방법을 설명 합니다.  
  
### <a name="to-compile-an-mfc-executable-or-regular-mfc-dll-by-using-clr"></a>/Clr을 사용 하 여 MFC 실행 파일 또는 일반 MFC DLL을 컴파일하려면  
  
1.  프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 클릭 하 고 **속성**합니다.  
  
2.  에 **프로젝트 속성** 대화 상자에서 노드 옆에 확장 **구성 속성** 선택 하 고 **일반**합니다. 오른쪽 창에서 아래 **프로젝트 기본값**설정, **공용 언어 런타임 지원** 를 **공용 언어 런타임 지원 (/ clr)** 합니다.  
  
     동일한 창에 있는지 확인 하는 **MFC 사용** 로 설정 된 **공유 DLL에서 MFC 사용**합니다.  
  
3.  아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **일반**합니다. 다음 사항을 확인 **디버깅 정보 형식** 로 설정 된 **프로그램 데이터베이스 /Zi** (하지 **/ZI**).  
  
4.  선택 된 **코드 생성** 노드. 설정 **최소 다시 빌드를 사용 하도록 설정** 를 **아니요 (/ Gm-)** 합니다. 또한 설정 **기본 런타임 검사** 를 **기본**합니다.  
  
5.  아래 **구성 속성**선택, **C/c + +** 차례로 **코드 생성**합니다. 다음 사항을 확인 **런타임 라이브러리** 로 설정 된 **다중 스레드 디버그 DLL (/ MDd)** 또는 **다중 스레드 DLL (/ MD)** 합니다.  
  
6.  Stdafx.h에서 다음 줄을 추가 합니다.  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
### <a name="to-compile-an-mfc-extension-dll-by-using-clr"></a>/Clr을 사용 하 여 MFC 확장 DLL을 컴파일하려면  
  
1.  컴파일하려면"MFC 실행 파일 또는 일반 MFC DLL /clr을 사용 하 여"의 단계를 수행 합니다.  
  
2.  아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **미리 컴파일된 헤더**합니다. 설정 **미리 컴파일된 헤더 만들기/사용** 를 **미리 컴파일된 헤더 사용 안 함**합니다.  
  
     대신에 **솔루션 탐색기**Stdafx.cpp 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다. 아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **일반**합니다. 설정 **공용 언어 런타임 지원을 사용 하 여 컴파일** 를 **공용 언어 런타임 지원 안 함**합니다.  
  
3.  DllMain과 포함 하는 파일에 대 한 호출에 **솔루션 탐색기**파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **일반**합니다. 오른쪽 창에서 아래 **프로젝트 기본값**설정, **공용 언어 런타임 지원을 사용 하 여 컴파일** 를 **공용 언어 런타임 지원 안 함**합니다.  
  
### <a name="to-compile-an-atl-executable-by-using-clr"></a>/Clr을 사용 하 여 ATL 실행 파일을 컴파일하려면  
  
1.  **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.  
  
2.  에 **프로젝트 속성** 대화 상자에서 노드 옆에 확장 **구성 속성** 선택 하 고 **일반**합니다. 오른쪽 창에서 아래 **프로젝트 기본값**설정, **공용 언어 런타임 지원** 를 **공용 언어 런타임 지원 (/ clr)** 합니다.  
  
3.  아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **일반**합니다. 다음 사항을 확인 **디버깅 정보 형식** 로 설정 된 **프로그램 데이터베이스 /Zi** (하지 **/ZI**).  
  
4.  선택 된 **코드 생성** 노드. 설정 **최소 다시 빌드를 사용 하도록 설정** 를 **아니요 (/ Gm-)** 합니다. 또한 설정 **기본 런타임 검사** 를 **기본**합니다.  
  
5.  아래 **구성 속성**선택, **C/c + +** 차례로 **코드 생성**합니다. 다음 사항을 확인 **런타임 라이브러리** 로 설정 된 **다중 스레드 디버그 DLL (/ MDd)** 또는 **다중 스레드 DLL (/ MD)** 합니다.  
  
6.  모든 있으므로 MIDL 생성 파일 (C 파일)의 경우에서 파일을 마우스 오른쪽 단추로 **솔루션 탐색기** 클릭 하 고 **속성**합니다. 아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **일반**합니다. 설정 **공용 언어 런타임 지원을 사용 하 여 컴파일** 를 **공용 언어 런타임 지원 안 함**합니다.  
  
### <a name="to-compile-an-atl-dll-by-using-clr"></a>/Clr을 사용 하 여 ATL DLL을 컴파일하려면  
  
1.  /Clr을 사용 하 여 ATL 실행 파일을 컴파일 "을" 섹션의 단계를 수행 합니다.  
  
2.  아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **미리 컴파일된 헤더**합니다. 설정 **미리 컴파일된 헤더 만들기/사용** 를 **미리 컴파일된 헤더 사용 안 함**합니다.  
  
     대신에 **솔루션 탐색기**Stdafx.cpp 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다. 아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **일반**합니다. 설정 **공용 언어 런타임 지원을 사용 하 여 컴파일** 를 **공용 언어 런타임 지원 안 함**합니다.  
  
3.  DllMain과 포함 하는 파일에 대 한 호출에 **솔루션 탐색기**파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 아래 **구성 속성**, 노드 옆에 확장 **C/c + +** 선택 **일반**합니다. 오른쪽 창에서 아래 **프로젝트 기본값**설정, **공용 언어 런타임 지원을 사용 하 여 컴파일** 를 **공용 언어 런타임 지원 안 함**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)