---
title: "CD2DBitmap 클래스 | Microsoft Docs"
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
  - "afxrendertarget/CD2DBitmap"
  - "CD2DBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmap 클래스"
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DBitmap 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1Bitmap에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|오버로드.  HBITMAP에서 CD2DBitmap 개체를 생성합니다.|  
|[CD2DBitmap::~CD2DBitmap](../Topic/CD2DBitmap::~CD2DBitmap.md)|소멸자  D2D 비트맵 개체가 소멸될 때 호출됩니다.|  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|오버로드.  CD2DBitmap 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmap::Attach](../Topic/CD2DBitmap::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DBitmap::CopyFromBitmap](../Topic/CD2DBitmap::CopyFromBitmap.md)|지정된 비트맵의 지정된 영역에서 현재 비트맵으로 복사합니다.|  
|[CD2DBitmap::CopyFromMemory](../Topic/CD2DBitmap::CopyFromMemory.md)|메모리의 지정된 영역에서 현재 비트맵으로 복사합니다.|  
|[CD2DBitmap::CopyFromRenderTarget](../Topic/CD2DBitmap::CopyFromRenderTarget.md)|지정된 렌더링 대상의 지정된 영역에서 현재 비트맵으로 복사합니다.|  
|[CD2DBitmap::Create](../Topic/CD2DBitmap::Create.md)|CD2DBitmap을 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DBitmap::Destroy](../Topic/CD2DBitmap::Destroy.md)|CD2DBitmap 개체를 소멸시킵니다.  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) 무시.\)|  
|[CD2DBitmap::Detach](../Topic/CD2DBitmap::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DBitmap::Get](../Topic/CD2DBitmap::Get.md)|ID2D1Bitmap 인터페이스를 반환합니다.|  
|[CD2DBitmap::GetDPI](../Topic/CD2DBitmap::GetDPI.md)|비트맵의 DPI를 반환합니다.|  
|[CD2DBitmap::GetPixelFormat](../Topic/CD2DBitmap::GetPixelFormat.md)|비트맵의 픽셀 형식 및 알파 모드를 검색합니다.|  
|[CD2DBitmap::GetPixelSize](../Topic/CD2DBitmap::GetPixelSize.md)|비트맵의 장치 독립적 단위\(픽셀\)의 크기를 반환합니다.|  
|[CD2DBitmap::GetSize](../Topic/CD2DBitmap::GetSize.md)|비트맵의 장치 독립적 픽셀\(DIP\)의 크기를 반환합니다.|  
|[CD2DBitmap::IsValid](../Topic/CD2DBitmap::IsValid.md)|리소스 유효성 검사\([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) 무시\)|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmap::CommonInit](../Topic/CD2DBitmap::CommonInit.md)|개체를 초기화합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmap::operator ID2D1Bitmap\*](../Topic/CD2DBitmap::operator%20ID2D1Bitmap*.md)|ID2D1Bitmap 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DBitmap::m\_bAutoDestroyHBMP](../Topic/CD2DBitmap::m_bAutoDestroyHBMP.md)|m\_hBmpSrc를 소멸시켜야 하는 경우 TRUE이고, 그렇지 않으면 FALSE입니다.|  
|[CD2DBitmap::m\_hBmpSrc](../Topic/CD2DBitmap::m_hBmpSrc.md)|원본 비트맵 핸들입니다.|  
|[CD2DBitmap::m\_lpszType](../Topic/CD2DBitmap::m_lpszType.md)|리소스 형식.|  
|[CD2DBitmap::m\_pBitmap](../Topic/CD2DBitmap::m_pBitmap.md)|ID2D1Bitmap 개체에 대한 포인터를 저장합니다.|  
|[CD2DBitmap::m\_sizeDest](../Topic/CD2DBitmap::m_sizeDest.md)|비트맵 대상 크기입니다.|  
|[CD2DBitmap::m\_strPath](../Topic/CD2DBitmap::m_strPath.md)|Botmap 파일 경로입니다.|  
|[CD2DBitmap::m\_uiResID](../Topic/CD2DBitmap::m_uiResID.md)|비트맵 리소스 ID입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBitmap](../../mfc/reference/cd2dbitmap-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)