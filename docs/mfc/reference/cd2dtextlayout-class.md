---
title: "CD2DTextLayout 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DTextLayout"
  - "afxrendertarget/CD2DTextLayout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DTextLayout 클래스"
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CD2DTextLayout 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

IDWriteTextLayout에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DTextLayout::CD2DTextLayout](../Topic/CD2DTextLayout::CD2DTextLayout.md)|CD2DTextLayout 개체를 생성합니다.|  
|[CD2DTextLayout::~CD2DTextLayout](../Topic/CD2DTextLayout::~CD2DTextLayout.md)|소멸자  D2D 텍스트 레이아웃 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DTextLayout::Create](../Topic/CD2DTextLayout::Create.md)|CD2DTextLayout을 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DTextLayout::Destroy](../Topic/CD2DTextLayout::Destroy.md)|CD2DTextLayout 개체를 소멸시킵니다.  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) 무시.\)|  
|[CD2DTextLayout::Get](../Topic/CD2DTextLayout::Get.md)|IDWriteTextLayout 인터페이스를 반환합니다.|  
|[CD2DTextLayout::GetFontFamilyName](../Topic/CD2DTextLayout::GetFontFamilyName.md)|텍스트의 글꼴 패밀리 이름을 지정된 위치에 복사합니다.|  
|[CD2DTextLayout::GetLocaleName](../Topic/CD2DTextLayout::GetLocaleName.md)|지정한 열 위치의 로캘 이름을 가져옵니다.|  
|[CD2DTextLayout::IsValid](../Topic/CD2DTextLayout::IsValid.md)|리소스 유효성 검사\([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) 무시\)|  
|[CD2DTextLayout::ReCreate](../Topic/CD2DTextLayout::ReCreate.md)|CD2DTextLayout을 다시 만듭니다.  \([CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md) 무시.\)|  
|[CD2DTextLayout::SetFontFamilyName](../Topic/CD2DTextLayout::SetFontFamilyName.md)|지정한 텍스트 범위 내의 텍스트에 대해 null로 끝나는 글꼴 패밀리 이름을 설정합니다.|  
|[CD2DTextLayout::SetLocaleName](../Topic/CD2DTextLayout::SetLocaleName.md)|지정된 텍스트 범위 내에서 텍스트의 로캘 이름을 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DTextLayout::operator IDWriteTextLayout\*](../Topic/CD2DTextLayout::operator%20IDWriteTextLayout*.md)|IDWriteTextLayout 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DTextLayout::m\_pTextLayout](../Topic/CD2DTextLayout::m_pTextLayout.md)|IDWriteTextLayout에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)