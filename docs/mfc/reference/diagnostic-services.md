---
title: "진단 서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "진단, 진단 함수 및 변수"
  - "진단, 진단 서비스"
  - "진단, 일반 MFC 목록"
  - "진단 함수 및 변수"
  - "진단 매크로"
  - "진단 매크로, 일반 MFC 목록"
  - "진단 서비스"
  - "진단, 진단 함수 및 변수"
  - "진단, 진단 서비스"
  - "진단, 일반 MFC 목록"
  - "일반 진단 함수 및 변수"
  - "MFC 일반 진단 매크로"
  - "MFC, 진단 서비스"
  - "MFC 개체 진단 함수"
  - "서비스, 진단"
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# 진단 서비스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 라이브러리는 프로그램을 더 쉽게 디버그할 수 있는 많은 진단 서비스를 제공합니다. 이러한 진단 서비스에는 매크로 및 전역 함수가 포함되며, 이러한 함수를 통해 프로그램의 메모리 할당을 추적하고 런타임 중 개체의 내용을 덤프하고 런타임 중 디버깅 메시지를 인쇄할 수 있습니다. 진단 서비스의 매크로 및 전역 함수는 다음과 같은 범주로 그룹화됩니다.  
  
-   일반 진단 매크로  
  
-   일반 진단 함수 및 변수  
  
-   개체 진단 함수  
  
 이러한 매크로 및 함수는 MFC 디버그 및 릴리스 버전의 `CObject`에서 파생된 모든 클래스에서 사용할 수 있습니다. 그러나 `DEBUG_NEW` 및 **VERIFY**를 제외한 모든 매크로 및 함수가 릴리스 버전에서는 아무 작업도 하지 않습니다.  
  
 디버그 라이브러리에서, 할당된 모든 메모리 블록은 일련의 "보호 바이트"와 함께 묶입니다. 이러한 바이트가 잘못된 메모리 쓰기로 인해 교란되면 진단 루틴이 문제를 보고할 수 있습니다. 다음 줄을 포함하는 경우  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/CPP/diagnostic-services_1.cpp)]  
  
 구현 파일에서 **new**에 대한 모든 호출은 파일 이름 및 메모리 할당이 발생한 줄 번호를 저장합니다.[CMemoryState::DumpAllObjectsSince](../Topic/CMemoryState::DumpAllObjectsSince.md) 함수는 이 추가 정보를 표시하여 메모리 누수를 확인할 수 있도록 합니다. 또한 진단 출력에 대한 자세한 내용은 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 클래스를 참조하세요.  
  
 또한 C 런타임 라이브러리는 응용 프로그램을 디버그하는 데 사용할 수 있는 진단 함수 집합도 지원합니다. 자세한 내용은 런타임 라이브러리 참조에서 [루틴 디버그](../../c-runtime-library/debug-routines.md)를 참조하세요.  
  
### MFC 일반 진단 매크로  
  
|||  
|-|-|  
|[ASSERT](../Topic/ASSERT%20\(MFC\).md)|라이브러리의 디버그 버전에서 지정된 식의 값이 **FALSE**로 계산된 경우 메시지를 출력한 후 프로그램을 중단합니다.|  
|[ASSERT\_KINDOF](../Topic/ASSERT_KINDOF.md)|개체가 지정된 클래스의 개체인지 아니면 지정된 클래스에서 파생된 클래스의 개체인지 테스트합니다.|  
|[ASSERT\_VALID](../Topic/ASSERT_VALID.md)|해당 `AssertValid` 멤버 함수를 호출하여 개체의 내부 유효성을 테스트합니다. 일반적으로 `CObject`에서 재정의됩니다.|  
|[DEBUG\_NEW](../Topic/DEBUG_NEW.md)|메모리 누수를 쉽게 찾을 수 있도록 디버그 모드에서 모든 개체 할당에 파일 이름과 줄 번호를 제공합니다.|  
|[DEBUG\_ONLY](../Topic/DEBUG_ONLY.md)|**ASSERT**와 비슷하지만, 식의 값을 테스트하지는 않습니다. 디버그 모드에서만 실행해야 하는 코드에 유용합니다.|  
|[TRACE](../Topic/TRACE.md)|라이브러리의 디버그 버전에서 `printf`와 유사한 기능을 제공합니다.|  
|[VERIFY](../Topic/VERIFY.md)|**ASSERT**와 비슷하지만, 라이브러리의 릴리스 버전뿐만 아니라 디버그 버전에서도 식을 계산합니다.|  
  
### MFC 일반 진단 변수 및 함수  
  
|||  
|-|-|  
|[afxDump](../Topic/afxDump%20\(CDumpContext%20in%20MFC\).md)|[CDumpContext](../../mfc/reference/cdumpcontext-class.md) 정보를 디버거 출력 창 또는 디버그 터미널에 보내는 전역 변수입니다.|  
|[afxMemDF](../Topic/afxMemDF.md)|디버깅 메모리 할당자의 동작을 제어하는 전역 변수입니다.|  
|[AfxCheckError](../Topic/AfxCheckError.md)|전달된 **SCODE**를 테스트하여 오류인지 알아보고 오류인 경우 적절한 오류를 throw하는 데 사용하는 전역 변수입니다.|  
|[AfxCheckMemory](../Topic/AfxCheckMemory.md)|현재 할당된 모든 메모리의 무결성을 검사합니다.|  
|[AfxDump](../Topic/AfxDump%20\(MFC\).md)|디버거 내에 있는 동안 호출되는 경우 디버그하는 동안 개체의 상태를 덤프합니다.|  
|[AfxDumpStack](../Topic/AfxDumpStack.md)|현재 스택의 이미지를 생성합니다. 이 함수는 항상 정적으로 연결됩니다.|  
|[AfxEnableMemoryLeakDump](../Topic/AfxEnableMemoryLeakDump.md)|메모리 누수 덤프를 사용하도록 설정합니다.|  
|[AfxEnableMemoryTracking](../Topic/AfxEnableMemoryTracking.md)|메모리 추적을 켜고 끕니다.|  
|[AfxIsMemoryBlock](../Topic/AfxIsMemoryBlock.md)|메모리 블록이 제대로 할당되었는지 확인합니다.|  
|[AfxIsValidAddress](../Topic/AfxIsValidAddress.md)|메모리 주소 범위가 프로그램의 경계 내에 있는지 확인합니다.|  
|[AfxIsValidString](../Topic/AfxIsValidString.md)|문자열에 대한 포인터가 유효한지 여부를 결정합니다.|  
|[AfxSetAllocHook](../Topic/AfxSetAllocHook.md)|각 메모리 할당에서 함수 호출을 사용하도록 설정합니다.|  
  
### MFC 개체 진단 함수  
  
|||  
|-|-|  
|[AfxDoForAllClasses](../Topic/AfxDoForAllClasses.md)|런타임 형식 검사를 지원하는 모든 `CObject` 파생 클래스에서 지정된 함수를 실행합니다.|  
|[AfxDoForAllObjects](../Topic/AfxDoForAllObjects.md)|**new**와 함께 할당된 모든 `CObject` 파생 개체에서 지정된 함수를 실행합니다.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)