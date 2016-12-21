---
title: "CImageList Class | Microsoft Docs"
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
  - "CImageList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList class"
  - "image lists [C++], CImageList class"
  - "Windows common controls [C++], CImageList"
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
caps.latest.revision: 19
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CImageList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 일반 이미지 목록 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CImageList : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CImageList::CImageList](../Topic/CImageList::CImageList.md)|`CImageList` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CImageList::Add](../Topic/CImageList::Add.md)|이미지 또는 이미지를 이미지 목록에 추가합니다.|  
|[CImageList::Attach](../Topic/CImageList::Attach.md)|연결 된 이미지 목록에 있는 `CImageList` 개체입니다.|  
|[CImageList::BeginDrag](../Topic/CImageList::BeginDrag.md)|이미지를 드래그 하기 시작 합니다.|  
|[CImageList::Copy](../Topic/CImageList::Copy.md)|내 이미지를 복사 하는 `CImageList` 개체입니다.|  
|[CImageList::Create](../Topic/CImageList::Create.md)|이미지 목록 초기화 하 고 연결 하는 `CImageList` 개체입니다.|  
|[CImageList::DeleteImageList](../Topic/CImageList::DeleteImageList.md)|이미지 목록에서 삭제합니다.|  
|[CImageList::DeleteTempMap](../Topic/CImageList::DeleteTempMap.md)|호출의  [CWinApp](../../mfc/reference/cwinapp-class.md) 유휴 시간 모든 임시 삭제 처리기 `CImageList` 개체에서 만든 `FromHandle`.|  
|[CImageList::Detach](../Topic/CImageList::Detach.md)|이미지 목록 개체에서 분리 된 `CImageList` 개체 및 이미지 목록에 있는 핸들을 반환 합니다.|  
|[CImageList::DragEnter](../Topic/CImageList::DragEnter.md)|끌기 작업 동안 업데이트를 잠그고 끌기 이미지를 지정 된 위치에 표시 합니다.|  
|[CImageList::DragLeave](../Topic/CImageList::DragLeave.md)|창의 잠금을 해제 하 고 창 업데이트 될 수 있도록 끌어서 이미지를 숨깁니다.|  
|[CImageList::DragMove](../Topic/CImageList::DragMove.md)|끌어서 놓기 작업 중에 끌고 이미지를 이동 합니다.|  
|[CImageList::DragShowNolock](../Topic/CImageList::DragShowNolock.md)|표시 하거나 창의 잠그지 않고 끄는 동안 끌어서 이미지를 숨깁니다.|  
|[CImageList::Draw](../Topic/CImageList::Draw.md)|끌어서 놓기 작업 중에 끌고 이미지를 그립니다.|  
|[CImageList::DrawEx](../Topic/CImageList::DrawEx.md)|이미지 목록 항목에 지정 된 장치 컨텍스트 그립니다.  지정 된 그리기 스타일을 사용 하 여 함수와 이미지에 지정 된 색을 혼합 합니다.|  
|[CImageList::DrawIndirect](../Topic/CImageList::DrawIndirect.md)|이미지 목록에서 이미지를 그립니다.|  
|[CImageList::EndDrag](../Topic/CImageList::EndDrag.md)|끌기 작업이 끝납니다.|  
|[CImageList::ExtractIcon](../Topic/CImageList::ExtractIcon.md)|이미지와 이미지 목록에서 마스크를 기반으로 하는 아이콘을 만듭니다.|  
|[CImageList::FromHandle](../Topic/CImageList::FromHandle.md)|반환에 대 한 포인터는 `CImageList` 개체 핸들 이미지 목록에 지정 되 면.  경우는 `CImageList` 개체의 핸들을 임시 연결 되어 있지 않습니다 `CImageList` 개체를 만들고 연결 합니다.|  
|[CImageList::FromHandlePermanent](../Topic/CImageList::FromHandlePermanent.md)|반환에 대 한 포인터는 `CImageList` 개체 핸들 이미지 목록에 지정 되 면.  경우는 `CImageList` 개체 핸들에 연결 되어 있지 않습니다  **NULL** 이 반환 됩니다.|  
|[CImageList::GetBkColor](../Topic/CImageList::GetBkColor.md)|이미지 목록에 대 한 현재 배경 색을 검색합니다.|  
|[CImageList::GetDragImage](../Topic/CImageList::GetDragImage.md)|드래그를 하는 데 사용 되는 임시 이미지 목록을 가져옵니다.|  
|[CImageList::GetImageCount](../Topic/CImageList::GetImageCount.md)|이미지 목록의 이미지 개수를 검색 합니다.|  
|[CImageList::GetImageInfo](../Topic/CImageList::GetImageInfo.md)|이미지에 대 한 정보를 검색합니다.|  
|[CImageList::GetSafeHandle](../Topic/CImageList::GetSafeHandle.md)|검색  **m\_hImageList**.|  
|[CImageList::Read](../Topic/CImageList::Read.md)|이미지 목록에서 보관 파일을 읽습니다.|  
|[CImageList::Remove](../Topic/CImageList::Remove.md)|이미지 목록에서 이미지를 제거합니다.|  
|[CImageList::Replace](../Topic/CImageList::Replace.md)|이미지 목록에서 이미지를 새 이미지로 대체합니다.|  
|[CImageList::SetBkColor](../Topic/CImageList::SetBkColor.md)|이미지 목록에 대 한 배경 색을 설정 합니다.|  
|[CImageList::SetDragCursorImage](../Topic/CImageList::SetDragCursorImage.md)|새 끌기 이미지를 만듭니다.|  
|[CImageList::SetImageCount](../Topic/CImageList::SetImageCount.md)|이미지 목록의 이미지 개수를 다시 설정합니다.|  
|[CImageList::SetOverlayImage](../Topic/CImageList::SetOverlayImage.md)|이미지의 인덱스를 오버레이 마스크로 사용할 이미지 목록에 추가 합니다.|  
|[CImageList::Write](../Topic/CImageList::Write.md)|이미지 목록 아카이브를 작성합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CImageList::operator HIMAGELIST](../Topic/CImageList::operator%20HIMAGELIST.md)|반환 된 `HIMAGELIST` 연결을 `CImageList`.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CImageList::m\_hImageList](../Topic/CImageList::m_hImageList.md)|이 개체에 연결 된 이미지 목록에 포함 하는 핸들입니다.|  
  
## 설명  
 "이미지 목록" 각각에 해당 인덱스에서 참조 될 수 있습니다 동일한 크기의 이미지의 컬렉션입니다.  이미지 목록 대량의 아이콘이 나 비트맵을 효율적으로 관리 하는 데 사용 됩니다.  이미지 목록의 모든 이미지는 화면 장치 형식의 단일, 와이드 비트맵에 포함 되어 있습니다.  이미지 목록 포함 마스크 아이콘 스타일으로 투명 하 게 이미지를 그리는 데 사용 되는 단색 비트맵도 포함할 수 있습니다.  Microsoft Win32 응용 프로그래밍 인터페이스 \(API\)를 사용 하 여 이미지를 그리는, 및 이미지 목록을 소멸 추가 및 이미지 제거, 이미지 바꾸기, 병합 이미지를 만들고 이미지를 끌어 이미지 목록 기능을 제공 합니다.  
  
 이 컨트롤 \(즉의 `CImageList` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 사용에 대 한 자세한 내용은 `CImageList`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CImageList를 사용 하 여](../../mfc/using-cimagelist.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl Class](../../mfc/reference/ctabctrl-class.md)