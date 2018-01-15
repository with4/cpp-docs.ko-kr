---
title: "TN030: 인쇄 및 인쇄 미리 보기 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.print
dev_langs: C++
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa11c30fb41630a5b293698fe3e69a80509f3f2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030: 인쇄 및 인쇄 미리 보기 사용자 지정
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트는 인쇄 및 인쇄 미리 보기를 사용자 지정 하는 과정을 설명 하 고에 사용 되는 콜백 루틴의 용도 설명 `CView` 콜백 루틴 및의 멤버 함수 및 **CPreviewView**합니다.  
  
## <a name="the-problem"></a>문제  
 인쇄 미리 보기 필요한 및 MFC 대부분 인쇄를 위한 완벽 한 솔루션을 제공 합니다. 대부분의 경우에서 거의 추가 코드는 인쇄를 미리 볼 수는 보기를 포함 하는 데 필요 합니다. 그러나 가지가 인쇄 성능을 최적화 하려면 중요 한 작업, 즉 개발자 부담도 필요로 하는 있으며 일부 응용 프로그램에서 인쇄 미리 보기 모드에 특정 사용자 인터페이스 요소를 추가 해야 합니다.  
  
## <a name="efficient-printing"></a>효율적인 인쇄  
 MFC 응용 프로그램은 표준 방법을 사용 하 여이 출력 하는 경우 Windows는 메모리 내 메타 파일에 모든 그래픽 장치 인터페이스 (GDI) 출력 호출 지시 합니다. 때 `EndPage` 은 호출, Windows는 프린터 한 페이지를 인쇄 하는 데 필요한 물리적 각 밴드에 대해 한 번씩 메타 파일을 재생 합니다. 이 렌더링 하는 동안 GDI 계속 해야 하는지 확인 하려면 중단 절차를 자주 쿼리. 일반적으로 중단 프로시저를 통해 사용자는 인쇄 대화 상자를 사용 하 여 인쇄 작업을 중단 될 수 있도록 처리할 메시지입니다.  
  
 그러나 인쇄 프로세스를 느려질 수 있습니다. 응용 프로그램의 인쇄 표준 기술을 사용 하 여 수행할 수 있는 보다 더 빠르게 이어야 하는 경우 수동 줄무늬를 구현 해야 합니다.  
  
## <a name="print-banding"></a>줄무늬 인쇄  
 수동으로 밴드 하기 위해 다시 구현 해야 인쇄 루프 되도록 `OnPrint` (대역 외) 당 한 번씩만 페이지당 여러 번 호출 됩니다. 인쇄 루프에서 구현 되는 **OnFilePrint** viewprnt.cpp의 함수입니다. 프로그램 `CView`-클래스를 파생 하 여 인쇄 함수를 호출 하는 명령을 처리 하는 인쇄에 대 한 메시지 맵 항목에이 함수를 오버 로드 합니다. 복사는 **OnFilePrint** 루틴와 줄무늬를 구현 하는 인쇄 루프를 변경 합니다. 것 줄무늬 사각형 인쇄 함수를 전달 인쇄 중인 페이지의 섹션에 따라 그리기를 최적화할 수 있도록 하려면.  
  
 둘째, 자주를 호출 해야 `QueryAbort` 밴드를 그리는 동안 합니다. 그렇지 않으면 중단 프로시저가 호출 되지 않습니다 하 고 사용자 인쇄 작업을 취소할 수 없게 됩니다.  
  
## <a name="print-preview-electronic-paper-with-user-interface"></a>사용자 인터페이스와 전자 문서 인쇄 미리 보기:  
 인쇄 미리 보기, 기본적으로 변환 프린터의 에뮬레이션에 표시 합니다. 기본적으로 주 창의 클라이언트 영역 창 내에서 완전 하 게 하나 또는 두 개의 페이지를 표시 하도록 사용 됩니다. 사용자는를 더 자세히 보려면 페이지의 영역을 확대 수 있습니다. 추가 지원과 함께 미리 보기 모드에서 문서를 편집 하려면 사용자도 사용할 수 있습니다.  
  
## <a name="customizing-print-preview"></a>인쇄 미리 보기를 사용자 지정  
 이 노트 다루기 인쇄 미리 보기 수정의 한 가지 측면인: 미리 보기 모드로 UI를 추가 합니다. 다른 수정 사항 가능 하지만 이러한 변경이이 토론의 범위를 벗어납니다.  
  
## <a name="to-add-ui-to-the-preview-mode"></a>미리 보기 모드에 UI를 추가 하려면  
  
1.  뷰 클래스를 파생 **CPreviewView**합니다.  
  
2.  원하는 UI 측면에 대 한 명령 처리기를 추가 합니다.  
  
3.  화면에 시각적 측면을 추가 하는 경우 재정의 `OnDraw` 호출한 후에 그리기를 수행 하 고 **CPreviewView::OnDraw 합니다.**  
  
## <a name="onfileprintpreview"></a>OnFilePrintPreview  
 인쇄 미리 보기에 대 한 명령 처리기입니다. 다음은 기본 구현이입니다.  
  
```  
void CView::OnFilePrintPreview()  
{ *// In derived classes,
    implement special window handling here *// Be sure to Unhook Frame Window close if hooked.  
 *// must not create this on the frame. Must outlive this function  
    CPrintPreviewState* pState = new CPrintPreviewState;  
 
    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR,
    this,  
    RUNTIME_CLASS(CPreviewView),
    pState))  
 { *// In derived classes,
    reverse special window handling *// here for Preview failure case  
 
    TRACE0("Error: DoPrintPreview failed");

    AfxMessageBox(AFX_IDP_COMMAND_FAILURE);

 delete pState;      // preview failed to initialize, *// delete State now  
 }  
}  
```  
  
 **DoPrintPreview** 응용 프로그램의 기본 창 숨겨집니다. 컨트롤 막대, 상태 표시줄 같은 보존할 수 있습니다는 pState에 지정 하 여->**dwStates** 멤버 (이 비트 마스크 이며 개별 컨트롤 막대에 대 한 비트가 정의한 **AFX_CONTROLBAR_MASK**(AFX_IDW_MYBAR)). 창 pState->**nIDMainPane** 는 자동으로 숨기 거 나 reshown 창입니다. **DoPrintPreview** 표준 미리 보기 UI에는 두 단추 모음을 만듭니다. 특별 한 창을 처리가 필요 하기 전에 수행 해야 하는 다른 창을 표시 하거나 숨길 등에 **DoPrintPreview** 호출 됩니다.  
  
 기본적으로 인쇄 미리 보기에는 다음이 완료 되 면 반환 컨트롤 막대의 원래 상태를 기본 창에 표시 합니다. 특별 한 처리가 필요한 경우 재정의에서 수행할 수 해야 **EndPrintPreview 합니다.** 경우 **DoPrintPreview** 실패도 특수 처리를 제공 합니다.  
  
 DoPrintPreview 호출 됩니다.  
  
-   미리 보기 도구 모음에 대 한 대화 상자 템플릿의 리소스 ID입니다.  
  
-   인쇄 미리 보기에는 인쇄를 수행 하는 보기를 포인터입니다.  
  
-   미리 보기 뷰 클래스의 런타임 클래스입니다. 이 DoPrintPreview에서 동적으로 생성 됩니다.  
  
-   CPrintPreviewState 포인터입니다. CPrintPreviewState 구조 (또는 파생된 구조 응용 프로그램이 자세한 상태를 유지 해야 하는 경우) 해야 *하지* 프레임에 만들 수 있습니다. DoPrintPreview 모덜리스 이며이 구조는 EndPrintPreview를 호출할 때까지 유지 해야 합니다.  
  
    > [!NOTE]
    >  인쇄 지원을 위한 개별 보기 또는 뷰 클래스를 필요한 경우 해당 개체에 대 한 포인터는 두 번째 매개 변수로 전달 되어야 합니다.  
  
## <a name="endprintpreview"></a>EndPrintPreview  
 인쇄 미리 보기 모드를 종료 하는이 호출 됩니다. 인쇄 미리 보기에 마지막 표시 된 문서에서 페이지를 이동 하는 것이 좋습니다. **EndPrintPreview** 작업을 수행 하는 응용 프로그램의 확률이 합니다. ->는 pInfo`m_nCurPage` 멤버는 마지막 (가장 왼쪽에 있는 두 페이지가 표시 된 경우), 표시 된 페이지가 고 포인터가 위치 페이지에서 사용자와 관련 하는지에 대 한 힌트입니다. 응용 프로그램의 보기의 구조를 프레임 워크에 알 수 없는 이후 선택한 위치로 이동 하는 코드를 제공 해야 합니다.  
  
 대부분의 동작 호출 하기 전에 수행 해야 **CView::EndPrintPreview**합니다. 이 호출의 결과 반대로 바꿉니다. **DoPrintPreview** pView 하 부 pInfo 삭제 합니다.  
  
```  
// Any further cleanup should be done here.  
CView::EndPrintPreview(pDC,
    pInfo,
    point,
    pView);
```  
  
## <a name="cwinapponfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 인쇄 설정 메뉴 항목에 대 한 매핑되어 있어야 합니다. 대부분의 경우에서 구현을 재정의 하는 데 필요한있지 않습니다.  
  
## <a name="page-nomenclature"></a>페이지 용어 체계  
 또 다른 문제는 페이지 번호 매기기 및 순서입니다. 간단한 워드 프로세서 유형 응용 프로그램에 대 한 간단한 문제입니다. 대부분의 인쇄 미리 보기 시스템 각 인쇄 된 페이지 문서에서 한 페이지에 해당 하는지 가정 합니다.  
  
 일반화 된 솔루션을 제공 하는 동안에 고려해 야 할 몇 가지 있습니다. CAD 시스템을 가정해 보세요. 사용자에 게 드로잉을 여러 전자 크기 시트에 설명 합니다. 전자 크기에서 (또는 더 작은 크기 조정 된) 플로터, 페이지 번호 매기기 것이 단순한 경우와 같이 합니다. 아니지만 레이저 프린터, 인쇄으로 16 크기는 페이지에서 어떤 인쇄 미리 보기 "페이지"  
  
 소개 단락 상태 대로 인쇄 미리 보기는 프린터와 같은 역할입니다. 따라서 사용자는 어떻게 선택 되어 있는 특정 프린터 나오는 것 표시 됩니다. 뷰에서 어떤 이미지는 각 페이지에 인쇄 됩니다.  
  
 페이지 설명 문자열에는 `CPrintInfo` 구조 제공 페이지당 하나의 수로 나타낼 수 있는 사용자에 게 페이지 번호를 표시 하는 방법 ("1 페이지"와 같이 또는 "페이지 1-2"). 기본 구현에서이 문자열은 사용 **CPreviewView::OnDisplayPageNumber**합니다. 다른 디스플레이 필요한 경우 예를 들어 "Sheet1 섹션 A, B"를 제공 하려면이 가상 함수를 재정의할 수 있습니다 하나.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

