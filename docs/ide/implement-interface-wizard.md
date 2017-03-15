---
title: "인터페이스 구현 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.impl.interface.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인터페이스 구현 마법사[C++]"
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 인터페이스 구현 마법사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 마법사에서는 COM 개체의 인터페이스를 구현합니다.  Visual Studio와 Windows에서 사용할 수 있는 COM 라이브러리에는 여러 인터페이스 구현이 포함됩니다.  해당 개체의 인스턴스를 만들 경우 인터페이스 구현 작업은 개체와 연관되며, 개체에서 제공하는 서비스를 제공합니다.  
  
 인터페이스와 구현에 대한 설명은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [Interfaces and Interface Implementations](http://msdn.microsoft.com/library/windows/desktop/ms694356)을 참조하십시오.  
  
 **구현할 인터페이스 위치**  
 인터페이스가 만들어지는 형식 라이브러리의 위치를 나타냅니다.  
  
|옵션|설명|  
|--------|--------|  
|**프로젝트**|형식 라이브러리가 프로젝트의 일부입니다.|  
|**레지스트리**|형식 라이브러리가 시스템에 등록됩니다.  등록된 형식 라이브러리는 **사용 가능한 형식 라이브러리**에 표시됩니다.|  
|**파일**|형식 라이브러리가 반드시 시스템에 등록되지는 않지만 파일에는 포함됩니다.  **위치**에 파일 위치를 지정해야 합니다.|  
  
 **사용 가능한 형식 라이브러리**  
 구현할 수 있는 인터페이스 정의가 포함된 사용 가능한 형식 라이브러리를 표시합니다.  **구현할 인터페이스 위치**에서 **파일**을 클릭하는 경우에는 이 상자에서 변경할 수 없습니다.  
  
 **위치**  
 **사용 가능한 형식 라이브러리** 목록에서 현재 선택된 형식 라이브러리의 위치를 표시합니다.  **구현할 인터페이스 위치**에서 **파일**을 선택한 경우에는 줄임표\(...\) 단추를 클릭하여 사용할 형식 라이브러리가 포함된 파일을 찾습니다.  
  
 **인터페이스**  
 **사용 가능한 형식 라이브러리** 상자에서 현재 선택된 형식 라이브러리에 해당 정의가 포함되어 있는 인터페이스를 표시합니다.  
  
> [!NOTE]
>  선택한 개체에 의해 이미 구현된 인터페이스와 같은 이름을 가진 인터페이스는 **인터페이스** 상자에 표시되지 않습니다.  
  
|전송 단추|설명|  
|-----------|--------|  
|**\>**|**인터페이스** 목록에서 현재 선택된 인터페이스 이름을 **인터페이스 구현** 목록에 추가합니다.|  
|**\>\>**|**인터페이스**목록에서 사용할 수 있는 모든 인터페이스 이름을 **인터페이스 구현** 목록에 추가합니다.|  
|**\<**|**인터페이스 구현** 목록에서 현재 선택된 인터페이스 이름을 제거합니다.|  
|**\<\<**|**인터페이스 구현** 목록에 현재 표시되어 있는 인터페이스 이름을 모두 제거합니다.|  
  
 **인터페이스 구현**  
 개체에 대해 구현하기로 선택한 인터페이스 이름을 표시합니다.  
  
> [!NOTE]
>  `IDispatch`에서 파생된 인터페이스를 둘 이상 포함하거나 클래스에 이미 있는 다른 인터페이스로부터 파생된 인터페이스를 구현하려면 COM\_MAP 엔트리를 명확히 지정해야 합니다.  자세한 내용은 [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md)를 참조하십시오.  
  
## 참고 항목  
 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md)