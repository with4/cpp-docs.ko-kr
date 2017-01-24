---
title: "그래픽 개체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HRGN"
  - "HFONT"
  - "HBITMAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "비트맵[C++], 장치 컨텍스트에서 만들기"
  - "브러시, 장치 컨텍스트에서 만들기"
  - "CBitmap 클래스, HBITMAP 핸들 형식"
  - "CBrush 클래스, HBRUSH 핸들 형식"
  - "CFont 클래스, HFONT 핸들 형식"
  - "CPalette 클래스, HPALETTE 핸들 형식"
  - "CPen 클래스, HPEN 핸들 형식"
  - "CRgn 클래스, HRGN 핸들 형식"
  - "장치 컨텍스트, 그래픽 개체"
  - "그리기, 장치 컨텍스트에서"
  - "글꼴[C++], 장치 컨텍스트에서 만들기"
  - "GDI[C++], 그래픽 개체 클래스"
  - "GDI 개체[C++]"
  - "GDI 개체[C++], 그래픽 개체 클래스"
  - "그래픽 개체"
  - "그래픽 개체, 장치 컨텍스트에서 만들기"
  - "HBITMAP 및 클래스 CBitmap"
  - "HBRUSH 및 클래스 CBrush"
  - "HFONT 및 클래스 CFont"
  - "HPALETTE 및 클래스 CPalette"
  - "HPEN"
  - "HRGN"
  - "이미지[C++], 그래픽 개체"
  - "메모리[C++], 디스플레이 컨텍스트"
  - "MFC, 그래픽 개체"
  - "개체[C++], 그래픽"
  - "개체[C++], 그래픽 개체"
  - "그리기 및 장치 컨텍스트"
  - "색상표 개체"
  - "색상표, 장치 컨텍스트에서 만들기"
  - "펜 개체"
  - "펜, 장치 컨텍스트에서 만들기"
  - "영역 개체"
  - "영역, 장치 컨텍스트에서 만들기"
ms.assetid: 41963b25-34b7-4343-8446-34ba516b83ca
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 그래픽 개체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows는 디바이스 컨텍스트에서 사용할 수 있는 다양한 그리기 도구를 제공합니다.  선을 그리는 펜, 내부를 채우는 브러시 및 텍스트를 그리는 글꼴을 제공합니다.  MFC는 Windows의 그리기 도구에 해당하는 그래픽 개체 클래스를 제공합니다.  아래 표에서는 사용 가능한 클래스와 그에 해당하는 Windows GDI\(그래픽 장치 인터페이스\) 핸들 형식을 보여 줍니다.  
  
> [!NOTE]
>  GDI\+는 Windows XP에 포함되어 있으며 Windows NT 4.0 SP6, Windows 2000, Windows 98 및 Windows Me의 재배포 가능 구성 요소로 제공됩니다.  최신 재배포 가능 구성 요소를 다운로드하려면 [http:\/\/www.microsoft.com\/msdownload\/platformsdk\/sdkupdate\/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm)을 참조하세요.  자세한 내용은 MSDN의 GDI\+ SDK 설명서\([http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/gdicpp\/GDIPlus\/GDIPlus.asp](http://msdn.microsoft.com/library/default.asp?url=/library/gdicpp/GDIPlus/GDIPlus.asp)\)를 참조하세요.  
  
 이 문서에서는 이러한 그래픽 개체 클래스의 사용에 대해 설명합니다.  
  
### Windows GDI 개체에 대한 클래스  
  
|클래스|Windows 핸들 형식|  
|---------|-------------------|  
|[CPen](../mfc/reference/cpen-class.md)|`HPEN`|  
|[CBrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|  
|[CFont](../mfc/reference/cfont-class.md)|**HFONT**|  
|[CBitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|  
|[CPalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|  
|[CRgn](../mfc/reference/crgn-class.md)|**HRGN**|  
  
> [!NOTE]
>  클래스 [CImage](../atl-mfc-shared/reference/cimage-class.md)에서는 향상된 비트맵 지원 기능을 제공합니다.  
  
 클래스 라이브러리의 각 그래픽 개체 클래스에는 해당 클래스의 그래픽 개체를 만들 수 있는 생성자가 있으며, `CreatePen`과 같은 적절한 만들기 함수를 사용하여 초기화해야 합니다.  
  
 클래스 라이브러리의 각 그래픽 개체 클래스에는 MFC 개체를 연결된 Windows 핸들에 캐스트하는 캐스트 연산자가 있습니다.  결과 핸들은 연결된 개체가 분리될 때까지 유효합니다.  핸들을 분리하려면 개체의 **Detach** 멤버 함수를 사용하세요.  
  
 다음 코드에서는 `CPen` 개체를 Windows 핸들에 캐스트합니다.  
  
 [!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/CPP/graphic-objects_1.cpp)]  
  
#### 디바이스 컨텍스트에서 그래픽 개체를 만들려면  
  
1.  스택 프레임에 그래픽 개체를 정의합니다.  `CreatePen`과 같은 형식별 만들기 함수를 사용하여 개체를 초기화합니다.  또는 생성자에서 개체를 초기화합니다.  예제 코드를 제공하는 [1단계 및 2단계 만들기](../mfc/one-stage-and-two-stage-construction-of-objects.md)의 설명을 참조하세요.  
  
2.  [개체를 선택하여 현재 디바이스 컨텍스트로 넣어](../mfc/selecting-a-graphic-object-into-a-device-context.md) 이전에 선택한 이전 그래픽 개체를 저장합니다.  
  
3.  현재 그래픽 개체 작업이 완료되면 이전 그래픽 개체를 선택하여 디바이스 컨텍스트로 다시 넣고 해당 상태를 복원합니다.  
  
4.  범위가 종료되면 프레임 할당 그래픽 개체가 자동으로 삭제되도록 합니다.  
  
> [!NOTE]
>  그래픽 개체를 반복해서 사용하려는 경우 한 번 할당한 다음 필요할 때마다 선택하여 디바이스 컨텍스트로 넣을 수 있습니다.  더 이상 필요 없는 경우에는 이러한 개체를 삭제해야 합니다.  
  
### 추가 정보  
  
-   [1단계 및 2단계 그래픽 개체 생성](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [1단계 및 2단계의 펜 생성 예제](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [그래픽 개체를 선택하여 장치 컨텍스트로 넣기](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [디바이스 컨텍스트](../mfc/device-contexts.md)  
  
-   [이전 운영 체제의 CImage 제한 사항](../mfc/cimage-limitations-with-earlier-operating-systems.md)  
  
## 참고 항목  
 [창 개체](../mfc/window-objects.md)