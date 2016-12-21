---
title: "CD2DBitmapBrush 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DBitmapBrush"
  - "afxrendertarget/CD2DBitmapBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmapBrush 클래스"
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DBitmapBrush 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1BitmapBrush에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](../Topic/CD2DBitmapBrush::CD2DBitmapBrush.md)|오버로드.  파일에서 CD2DBitmapBrush 개체를 생성합니다.|  
|[CD2DBitmapBrush::~CD2DBitmapBrush](../Topic/CD2DBitmapBrush::~CD2DBitmapBrush.md)|소멸자  D2D 비트맵 브러시 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmapBrush::Attach](../Topic/CD2DBitmapBrush::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DBitmapBrush::Create](../Topic/CD2DBitmapBrush::Create.md)|CD2DBitmapBrush를 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DBitmapBrush::Destroy](../Topic/CD2DBitmapBrush::Destroy.md)|CD2DBitmapBrush 개체를 소멸시킵니다.  \([CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md) 무시.\)|  
|[CD2DBitmapBrush::Detach](../Topic/CD2DBitmapBrush::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DBitmapBrush::Get](../Topic/CD2DBitmapBrush::Get.md)|ID2D1BitmapBrush 인터페이스를 반환합니다.|  
|[CD2DBitmapBrush::GetBitmap](../Topic/CD2DBitmapBrush::GetBitmap.md)|이 브러시가 그리는 데 사용하는 비트맵의 소스를 가져옵니다.|  
|[CD2DBitmapBrush::GetExtendModeX](../Topic/CD2DBitmapBrush::GetExtendModeX.md)|브러시가 비트맵을 지나 확장되는 영역을 수평으로 바둑판식으로 표시하는 메서드를 가져옵니다.|  
|[CD2DBitmapBrush::GetExtendModeY](../Topic/CD2DBitmapBrush::GetExtendModeY.md)|브러시가 비트맵을 지나 확장되는 영역을 수직으로 바둑판식으로 표시하는 메서드를 가져옵니다.|  
|[CD2DBitmapBrush::GetInterpolationMode](../Topic/CD2DBitmapBrush::GetInterpolationMode.md)|브러시 비트맵을 크기 조정 또는 회전할 때 사용되는 보간 메서드를 가져옵니다.|  
|[CD2DBitmapBrush::SetBitmap](../Topic/CD2DBitmapBrush::SetBitmap.md)|이 브러시가 그리는 데 사용하는 비트맵의 소스를 지정합니다.|  
|[CD2DBitmapBrush::SetExtendModeX](../Topic/CD2DBitmapBrush::SetExtendModeX.md)|브러시가 비트맵을 지나 확장되는 영역을 수평으로 바둑판식으로 표시되는 방법을 지정합니다.|  
|[CD2DBitmapBrush::SetExtendModeY](../Topic/CD2DBitmapBrush::SetExtendModeY.md)|브러시가 비트맵을 지나 확장되는 영역을 수직으로 바둑판식으로 표시되는 방법을 지정합니다.|  
|[CD2DBitmapBrush::SetInterpolationMode](../Topic/CD2DBitmapBrush::SetInterpolationMode.md)|브러시 비트맵을 크기 조정 또는 회전할 때 사용되는 보간 모드를 지정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmapBrush::CommonInit](../Topic/CD2DBitmapBrush::CommonInit.md)|개체를 초기화합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush\*](../Topic/CD2DBitmapBrush::operator%20ID2D1BitmapBrush*.md)|ID2D1BitmapBrush 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmapBrush::m\_pBitmap](../Topic/CD2DBitmapBrush::m_pBitmap.md)|CD2DBitmap 개체에 대한 포인터를 저장합니다.|  
|[CD2DBitmapBrush::m\_pBitmapBrush](../Topic/CD2DBitmapBrush::m_pBitmapBrush.md)|ID2D1BitmapBrush 개체에 대한 포인터를 저장합니다.|  
|[CD2DBitmapBrush::m\_pBitmapBrushProperties](../Topic/CD2DBitmapBrush::m_pBitmapBrushProperties.md)|비트맵 브러시 속성입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DBitmapBrush](../../mfc/reference/cd2dbitmapbrush-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)