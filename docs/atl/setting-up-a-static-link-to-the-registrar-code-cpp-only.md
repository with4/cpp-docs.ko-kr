---
title: "Setting Up a Static Link to the Registrar Code (C++ Only) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "링크[C++], to ATL Registrar code"
  - "statically linking to ATL Registrar code"
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Setting Up a Static Link to the Registrar Code (C++ Only)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C \+ \+ 클라이언트는 등록자 코드에 대 한 정적 링크를 만들 수 있습니다.  등록자 파서의 정적 링크 약 5kb를 릴리스 빌드에 추가.  
  
 지정한 정적 링크 설정 하는 가장 간단한 방법은 가정  [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md) 개체를 선언 합니다.  \(ATL에서 사용 되는 기본 사양입니다\)  
  
### DECLARE\_REGISTRY\_RESOURCEID를 사용 하 여 정적 링크를 만들려면  
  
1.  지정  [\/D](../build/reference/d-preprocessor-definitions.md)`_ATL_STATIC_REGISTRY` 대신 \/D**\_ATL\_DLL**.  
  
2.  다시 컴파일하십시오.  
  
## 참고 항목  
 [레지스트리 구성 요소\(등록자\)](../atl/atl-registry-component-registrar.md)