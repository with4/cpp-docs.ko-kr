---
title: "CAnimateCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimateCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "animation controls [C++], CAnimateCtrl class"
  - "CAnimateCtrl class"
  - "Windows common controls [C++], CAnimateCtrl class"
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CAnimateCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일반적인 애니메이션 Windows 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
  
class CAnimateCtrl : public CWnd  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimateCtrl::CAnimateCtrl](../Topic/CAnimateCtrl::CAnimateCtrl.md)|`CAnimateCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimateCtrl::Close](../Topic/CAnimateCtrl::Close.md)|AVI 클립을 닫습니다.|  
|[CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)|Animation 컨트롤을 만들고이에 연결 된 `CAnimateCtrl` 개체입니다.|  
|[CAnimateCtrl::CreateEx](../Topic/CAnimateCtrl::CreateEx.md)|지정한 Windows 확장된 스타일은 애니메이션 컨트롤을 만들고 연결 하는 `CAnimateCtrl` 개체입니다.|  
|[CAnimateCtrl::IsPlaying](../Topic/CAnimateCtrl::IsPlaying.md)|오디오 비디오 인터리브 \(AVI\) 클립을 재생 여부를 나타냅니다.|  
|[CAnimateCtrl::Open](../Topic/CAnimateCtrl::Open.md)|AVI 클립 파일 또는 리소스 파일에서 열고 첫 번째 프레임을 표시 합니다.|  
|[CAnimateCtrl::Play](../Topic/CAnimateCtrl::Play.md)|사운드 없이 AVI 클립을 재생합니다.|  
|[CAnimateCtrl::Seek](../Topic/CAnimateCtrl::Seek.md)|AVI 클립을 선택한 단일 프레임을 표시합니다.|  
|[CAnimateCtrl::Stop](../Topic/CAnimateCtrl::Stop.md)|AVI 클립의 재생을 중지 합니다.|  
  
## 설명  
 이 컨트롤 \(즉의 `CAnimateCtrl` 클래스\) Windows 95, Windows 98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 Animation 컨트롤 클립 AVI \(오디오 비디오 인터리브\) 형식으로 표시 하는 사각형 창입니다\-표준 Windows 비디오\/오디오 형식입니다.  AVI 클립은 동영상과 같은 비트맵 프레임 것입니다.  
  
 애니메이션 컨트롤에는 간단한 AVI 클립만 재생할 수 있습니다.  구체적으로 애니메이션 컨트롤에 의해 재생 되도록 클립 다음 요구 사항을 충족 해야 합니다.  
  
-   비디오 스트림을 하나만 있어야 하며 하나 이상의 프레임 있어야 합니다.  
  
-   있을 수 최대 두 개의 스트림을 파일에서 \(애니메이션 컨트롤 오디오 정보를 무시 하지만 일반적으로 다른 스트림에 있는 경우 오디오 스트림을입니다\).  
  
-   클립 수 압축 하거나 압축 RLE8 압축을 사용 합니다.  
  
-   색상표 변경에 비디오 스트림은 허용 됩니다.  
  
 AVI 파일을 별도 응용 프로그램 수와 함께 AVI 클립 AVI 리소스로 응용 프로그램에 추가할 수 있습니다.  
  
 AVI 클립이 표시 되는 동안 실행 스레드를 계속 하기 때문에 일반적으로 사용 하는 애니메이션 컨트롤에 대 한 긴 작업 동안 시스템 활동을 나타낼 것입니다.  예를 들어, 찾기 대화 상자의 파일 탐색기의 파일 검색으로 움직이는 돋보기를 표시합니다.  
  
 사용자가 만든 경우는 `CAnimateCtrl` 개체는 내에서 대화 상자 또는 대화 상자를 닫을 때 대화 상자 편집기를 사용 하 여 대화 상자 리소스를 자동으로 소멸 됩니다.  
  
 만들 경우는 `CAnimateCtrl` 개체는 창 내에서 파괴를 해야 합니다.  사용자가 만든 경우는 `CAnimateCtrl` 개체는 스택에 자동으로 소멸 됩니다.  만들 경우의 `CAnimateCtrl` 개체를 사용 하 여 힙에  **새** 해야 호출 함수를  **삭제** 개체 파괴를.  새 클래스에서 파생 하는 경우 `CAnimateCtrl` 및 해당 클래스의 모든 메모리 할당, 재정의 `CAnimateCtrl` 할당을 삭제 하는 소멸자입니다.  
  
 사용에 대 한 자세한 내용은 `CAnimateCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CAnimateCtrl 사용](../../mfc/using-canimatectrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)   
 [ON\_CONTROL](../Topic/ON_CONTROL.md)