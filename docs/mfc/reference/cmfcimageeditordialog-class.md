---
title: "CMFCImageEditorDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCImageEditorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImageEditorDialog class"
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCImageEditorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCImageEditorDialog` 클래스는 이미지 편집기 대화 상자를 지원 합니다.  
  
## 구문  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](../Topic/CMFCImageEditorDialog::CMFCImageEditorDialog.md)|`CMFCImageEditorDialog` 개체를 생성합니다.|  
  
## 설명  
 `CMFCImageEditorDialog` 포함 하는 대화 상자 클래스를 제공 합니다.  
  
-   이미지의 개별 픽셀을 수정 하는 데 사용 된 그림 영역입니다.  
  
-   그림 영역에 있는 픽셀을 수정 하는 도구를 그리기.  
  
-   드로잉 도구에 사용 되는 색을 지정 하는 색상 팔레트입니다.  
  
-   편집의 결과 표시 하는 미리 보기 영역입니다.  
  
 다음 그림에서는 이미지 편집기 대화 상자를 보여 줍니다.  
  
 ![CMFCImageEditorDialog 대화 상자](../../mfc/reference/media/imageedit.png "ImageEdit")  
  
 한 가지 방법은 사용 하는 `CMFCImageEditorDialog` 개체는이 전달 하는 `CBitmap` 이미지를 편집할 수.  큰 이미지를 이미지 편집 영역 제한 크기 있고 논리 픽셀 크기의 영역에 맞게 조정 됩니다 때문에 만들지 않습니다.  호출 하는 `DoModal` 메서드는 모달 대화 상자를 시작 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## 요구 사항  
 **헤더:** afximageeditordialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)