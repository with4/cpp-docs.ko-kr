---
title: "CBitmap Class | Microsoft Docs"
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
  - "CBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBitmap class"
  - "drawing, 도구"
  - "GDI bitmap"
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBitmap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 그래픽 장치 인터페이스 \(GDI\) 비트맵을 캡슐화 하 고 비트맵을 조작 하는 멤버 함수를 제공 합니다.  
  
## 구문  
  
```  
class CBitmap : public CGdiObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CBitmap::CBitmap](../Topic/CBitmap::CBitmap.md)|`CBitmap` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CBitmap::CreateBitmap](../Topic/CBitmap::CreateBitmap.md)|지정 된 너비, 높이 및 비트 패턴을 가진 메모리 장치 종속 비트맵을 사용 하 여 개체를 초기화 합니다.|  
|[CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)|\(지정 된 경우\) 비트맵 너비, 높이, 비트 패턴에서 개체 초기화는  **비트맵** 구조.|  
|[CBitmap::CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md)|지정한 장치와 호환 되는 비트맵을 사용 하 여 개체를 초기화 합니다.|  
|[CBitmap::CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md)|지정한 장치와 호환 되는 비트맵이 삭제 가능한 개체를 초기화 합니다.|  
|[CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md)|반환에 대 한 포인터는 `CBitmap` 개체 핸들은 Windows에 지정 되 면 `HBITMAP` 비트맵.|  
|[CBitmap::GetBitmap](../Topic/CBitmap::GetBitmap.md)|채우기는  **비트맵** 구조는 비트맵에 대 한 정보.|  
|[CBitmap::GetBitmapBits](../Topic/CBitmap::GetBitmapBits.md)|지정한 비트맵의 비트를 지정 된 버퍼에 복사합니다.|  
|[CBitmap::GetBitmapDimension](../Topic/CBitmap::GetBitmapDimension.md)|비트맵의 높이 너비를 반환합니다.  이전에 설정 된 것으로 간주 됩니다 높이 너비는  [SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md) 멤버 함수입니다.|  
|[CBitmap::LoadBitmap](../Topic/CBitmap::LoadBitmap.md)|응용 프로그램의 실행 파일에서 명명 된 비트맵 리소스를 로드 하 고 비트맵 개체에 연결 된 개체를 초기화 합니다.|  
|[CBitmap::LoadMappedBitmap](../Topic/CBitmap::LoadMappedBitmap.md)|비트맵을 로드 하 고 현재 시스템 색에 색을 매핑합니다.|  
|[CBitmap::LoadOEMBitmap](../Topic/CBitmap::LoadOEMBitmap.md)|미리 정의 된 Windows 비트맵 로드 및 비트맵 객체에 첨부 하 여 개체를 초기화 합니다.|  
|[CBitmap::SetBitmapBits](../Topic/CBitmap::SetBitmapBits.md)|비트의 비트맵 비트를 지정한 값으로 설정합니다.|  
|[CBitmap::SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md)|너비 및 높이를 0.1 밀리미터 단위로 비트맵 할당합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CBitmap::operator HBITMAP](../Topic/CBitmap::operator%20HBITMAP.md)|연결에 대 한 Windows 핸들을 반환의 `CBitmap` 개체입니다.|  
  
## 설명  
 사용 하는 `CBitmap` 개체, 개체를 생성, 비트맵 핸들 초기화 멤버 함수 중 하나에 연결할 수 있으며 다음 개체의 멤버 함수를 호출 합니다.  
  
 다음과 같이 그래픽 개체를 사용 하 여에 대 한 자세한 내용은 `CBitmap`를 참조 하십시오  [그래픽 개체](../../mfc/graphic-objects.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MDI MFC 샘플](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)