---
title: '방법: 기존 MFC 리본을 리본 리소스로 변환 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8024acc4abbb02b14ed968df83779d34bd4a7271
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351652"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>방법: 기존 MFC 리본을 리본 리소스로 변환
리본 리소스는 시각화를 수정 하 고 수동으로 코딩 된 리본 보다 유지 관리 하기 쉽습니다. 이 항목에서는 MFC 프로젝트에 수동으로 코딩 된 리본을 리본 리소스로 변환 하는 방법을 설명 합니다.  
  
 예를 들어, MFC 리본 클래스를 사용 하는 코드를 있는 기존 MFC 프로젝트 있어야 [CMFCRibbonBar 클래스](../mfc/reference/cmfcribbonbar-class.md)합니다.  
  
### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>MFC 리본을 리본 리소스로 변환 하려면  
  
1.  Visual Studio에서 기존 MFC 프로젝트에서 CMFCRibbonBar 개체를 초기화 하는 소스 파일을 엽니다. 일반적으로 mainfrm.cpp 파일이 있습니다. 리본 메뉴에 대 한 초기화 코드 뒤에 다음 코드를 추가 합니다.  
  
 ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");

 ```  
  
     파일을 저장한 후 닫습니다.  
  
2.  및 MFC 응용 프로그램을 실행 하 고 메모장에서 열고 RibbonOutput.txt 빌드하고 해당 내용을 복사 합니다.  
  
3.  Visual Studio에서에 **프로젝트** 메뉴를 클릭 하 여 **리소스 추가**합니다. 에 **리소스 추가** 대화 상자에서 **리본** 클릭 하 고 **새로**합니다.  
  
     Visual Studio는 리본 리소스를 만들고 디자인 뷰에서 열립니다. 리본 리소스 ID는 IDR_RIBBON1에 표시 되는 **리소스 뷰**합니다. 리본 메뉴 ribbon1.mfcribbon ms XML 파일에 정의 됩니다.  
  
4.  Visual Studio에서 ribbon1.mfcribbon ms를 열고 해당 내용을 삭제 RibbonOutput.txt으로, 앞에서 복사한 내용을 붙여 넣습니다. 저장 하 고 ribbon1.mfcribbon ms를 닫습니다.  
  
5.  다시 CMFCRibbonBar 개체를 초기화 하는 소스 파일을 엽니다 (일반적으로 mainfrm.cpp)을 주석으로 처리 하면 기존 코드를 리본. 주석으로 처리 하는 코드 뒤에 다음 코드를 추가 합니다.  
  
 ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);

 ```  
  
6.  프로젝트를 빌드하고 프로그램을 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리본 디자이너(MFC)](../mfc/ribbon-designer-mfc.md)

