---
title: "TN026: DDX 및 DDV 루틴 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DDX
- DDV
dev_langs: C++
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5a12ca508478b04a5485ad3f088009d7cd6b0b48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX 및 DDV 루틴
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트는 대화 상자 데이터 교환 (DDX) 및 대화 상자 데이터 유효성 검사 (DDV) 아키텍처를 설명합니다. 또한 DDX_ 나 DDV_ 프로시저를 작성 하는 방법 및 classwizard 함께 사용 하면 루틴을 사용 하도록 확장 하는 방법을 설명 합니다.  
  
## <a name="overview-of-dialog-data-exchange"></a>대화 상자 데이터 교환 개요  
 모든 대화 상자 데이터 함수는 c + + 코드도 수행 됩니다. 특별 한 리소스 또는 매직 매크로 없는 합니다. 메커니즘의 핵심은 하는 대화 상자 데이터 교환 모든 대화 상자 클래스에서 재정의 되는 가상 함수 및 유효성 검사. 항상이 폼에서 발견 되었습니다.  
  
```  
void CMyDialog::DoDataExchange(CDataExchange* pDX)  
{  
    CDialog::DoDataExchange(pDX);
*// call base class  
 *//{{AFX_DATA_MAP(CMyDialog)  
 <data_exchange_function_call>  
 <data_validation_function_call> *//}}AFX_DATA_MAP  
}  
```  
  
 특수 형식 AFX 주석을 사용할 경우 클래스 마법사를 찾아이 함수 내에서 코드를 편집 합니다. 클래스 마법사와 호환 되지 않는 코드가 특수 형식 주석 밖에 배치 되어야 합니다.  
  
 위의 예에서 < data_exchange_function_call >는 형태로 표현:  
  
```  
DDX_Custom(pDX,
    nIDC,
    field);
```  
  
 및 < data_validation_function_call >은 선택 사항이 며 형식:  
  
```  
DDV_Custom(pDX,
    field, ...);
```  
  
 둘 이상의 DDX_/DDV_ 쌍 각각에 포함 될 수 있습니다 `DoDataExchange` 함수입니다.  
  
 모든 대화 상자 데이터 교환 루틴 및 MFC와 함께 제공 되는 대화 상자 데이터 유효성 검사 루틴의 목록에 대 한 'afxdd_.h'를 참조 하십시오.  
  
 대화 상자 데이터는 해당:에 멤버 데이터는 **CMyDialog** 클래스입니다. 구조체 또는 유사 항목에 저장 되지 않습니다.  
  
## <a name="notes"></a>노트  
 파생 된 클래스에서 사용할 수 있는 모든 기능 "대화 상자 데이터" 라고 하지만 `CWnd` 및 정당한 대화 상자에 제한 되지 않습니다.  
  
 데이터의 초기 값이 블록에 일반적으로 표준 c + + 생성자에서 설정 됩니다 `//{{AFX_DATA_INIT` 및 `//}}AFX_DATA_INIT` 메모 합니다.  
  
 `CWnd::UpdateData`초기화 및 오류에 대 한 호출 주위 처리를 수행 하는 작업은 `DoDataExchange`합니다.  
  
 호출할 수 있습니다 `CWnd::UpdateData` 언제 든 지 데이터 교환 및 유효성 검사를 수행 합니다. 기본적으로 `UpdateData`기본에서 (TRUE) 라고 `CDialog::OnOK` 처리기 및 `UpdateData`기본에서 (FALSE) 라고 `CDialog::OnInitDialog`합니다.  
  
 DDV_ 루틴 바로 다음에 나와야 DDX_ 루틴에 대 한 *필드*합니다.  
  
## <a name="how-does-it-work"></a>어떻게 작동 합니까  
 대화 상자 데이터를 사용 하려면 다음을 이해 하 고 필요가 없습니다. 그러나이 원리를 자세히 파악할수록 작동 방식을 이해 교환 또는 유효성 검사 프로시저를 직접 작성 하는 데 도움이 됩니다.  
  
 `DoDataExchange` 멤버 함수는 것과 마찬가지로 `Serialize` -멤버 함수는를 가져오거나 설정할 데이터/외부 양식에서 (이 경우 대화 상자에서 제어) / 클래스에서 멤버 데이터에서 합니다. `pDX` 매개 변수 데이터 교환을 수행 하는 데 컨텍스트 이며는 비슷합니다는 `CArchive` 매개 변수를 `CObject::Serialize`합니다. `pDX` (한 `CDataExchange` 개체)의 비슷하게 플래그 방향이 `CArchive` 방향 플래그가:  
  
-   경우 **! m_bSaveAndValidate**, 다음 컨트롤에 데이터 상태를 로드 합니다.  
  
-   경우 `m_bSaveAndValidate`, 다음 컨트롤에서 데이터 상태를 설정 합니다.  
  
 유효성 검사에만 발생 때 `m_bSaveAndValidate` 설정 됩니다. 값 `m_bSaveAndValidate` BOOL 매개 변수를 따라 사용자가 `CWnd::UpdateData`합니다.  
  
 세 개의 다른 흥미로운 `CDataExchange` 구성원:  
  
- `m_pDlgWnd`: 창 (일반적으로 대화 상자) 컨트롤이 들어 있는입니다. 모든 DDX/DDV 루틴을를 't h i s'를 전달 하는 것과 DDX_ DDV_ 전역 함수 및 호출자가입니다.  
  
- `PrepareCtrl`및 `PrepareEditCtrl`: 데이터 교환에 대 한 대화 상자 컨트롤을 준비 합니다. 유효성 검사에 실패할 경우 포커스를 설정 하는 것에 대 한 해당 컨트롤의 핸들을 저장 합니다. `PrepareCtrl`nonedit 컨트롤에 사용 되 고 `PrepareEditCtrl` 편집 컨트롤에 사용 됩니다.  
  
- **실패**: 사용자 입력된 오류를 경고 메시지 상자를 표시 한 후 호출 합니다. 이 루틴 마지막 컨트롤에 포커스를 복원 합니다 (마지막으로 호출한 `PrepareCtrl` / `PrepareEditCtrl`) 예외를 throw 합니다. 이 멤버 함수는 DDX_와 DDV_ 루틴에서 호출할 수 있습니다.  
  
## <a name="user-extensions"></a>사용자 확장  
 기본 DDX/DDV 메커니즘을 확장 하는 방법은 여러 가지가 있습니다. 다음과 같은 작업을 수행할 수 있습니다.  
  
-   새 데이터 형식을 추가 합니다.  
  
 ```  
    CTime 
 ```  
  
-   새 exchange 프로시저 (DDX_)를 추가 합니다.  
  
 ```  
    void PASCAL DDX_Time(CDataExchange* pDX,
    int nIDC,
    CTime& tm);

 ```  
  
-   새 유효성 검사 프로시저 (DDV_)를 추가 합니다.  
  
 ```  
    void PASCAL DDV_TimeFuture(CDataExchange* pDX,
    CTime tm,
    BOOL bFuture);
*// make sure time is in the future or past  
 ```  
  
-   임의의 식 유효성 검사 프로시저에 전달 합니다.  
  
 ```  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxAge);

 ```  
  
    > [!NOTE]
    >  이러한 임의의 식 classwizard 함께 사용 하 여 편집할 수 없습니다 및 특수 형식 주석 외부로 이동할 수 해야 (/ / {{AFX_DATA_MAP(CMyClass)) 합니다.  
  
 있어야는 **DoDialogExchange** 조건부 또는 intermixed 교환 및 유효성 검사 함수 호출에 다른 유효한 c + + 문 멤버 함수를 포함 합니다.  
  
```  
//{{AFX_DATA_MAP(CMyClass)  
DDX_Check(pDX,
    IDC_SEX,
    m_bFemale);

DDX_Text(pDX,
    IDC_EDIT1,
    m_age);

//}}AFX_DATA_MAP  
if (m_bFemale)  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxFemaleAge);

else  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxMaleAge);
```  
  
> [!NOTE]
>  위에 나와 있는 것 처럼 이러한 코드 classwizard 함께 사용 하 여 편집할 수 없습니다 및 특수 형식 주석 외에 사용 해야 합니다.  
  
## <a name="classwizard-support"></a>클래스 마법사 지원  
 클래스 마법사 클래스 마법사 사용자 인터페이스에 사용자 고유의 DDX_ 및 DDV_ 루틴을 통합할 수 있으므로 DDX/DDV 사용자 지정 항목의 하위 집합을 지원 합니다. 프로젝트 또는 대부분의 프로젝트에서 특정 DDX 및 DDV 루틴을 다시 사용 하려는 경우 유용한만 비용은이 작업을 수행 합니다.  
  
 이 위해 특별 한 항목은 DDX에서 이루어집니다. CLW (이전 버전의 Visual c + + APSTUDIO이이 정보를 저장 하는 데 사용 합니다. INI) 또는 프로젝트의 합니다. CLW 파일입니다. 특별 한 항목 수의 프로젝트의 [일반 정보] 섹션에서 하나를 입력 합니다. CLW 파일 또는 DDX의 [ExtraDDX] 섹션에 있습니다. Files\microsoft Studio\Visual Visual C++ \bin 디렉터리에 CLW 파일입니다. DDX를 만들어야 할 수 있습니다. 존재 하지 않는 경우 CLW 파일입니다. 특정 프로젝트에만 사용자 지정 DDX_/DDV_ 루틴을 사용 하려는 경우 프로젝트의 [일반 정보] 섹션에 항목을 추가 합니다. CLW 대신 파일입니다. 여러 프로젝트에서 루틴을 사용 하려는 경우 DDX의 [ExtraDDX] 섹션에 항목을 추가 합니다. CLW 합니다.  
  
 이러한 특수 한 항목의 일반 형식은 다음과 같습니다.  
  
```  
ExtraDDXCount=n  
```  
  
 여기서 n은 따르도록 ExtraDDX 줄 수  
  
```  
ExtraDDX=<keys>;<vb-keys>; <prompt>; <type>; <initValue>; <DDX_Proc>  
[;<DDV_Proc>; <prompt1>; <arg1>; [<prompt2>; <fmt2>]]  
```  
  
 여기서는 1-n 정의 되는 목록에서 DDX 형식을 나타내는 숫자입니다.  
  
 각 필드가 ';'으로 구분 됩니다. 필드와 각각의 용도 다음과 같습니다.  
  
 \<키 >  
 이 변수 형식을 사용할 수 있는 대화 상자 컨트롤에 대 한을 나타내는 단일 문자 목록은 =입니다.  
  
 E = 편집  
  
 C = 두 가지 상태 확인란  
  
 c = 3 상 확인란  
  
 R = 그룹의 첫 번째 라디오 단추  
  
 L = 것이 더 효율적일된 목록 상자  
  
 l = 정렬 된 목록 상자  
  
 M = (편집 항목과) 콤보 상자  
  
 N = 것이 더 효율적일된 드롭 목록  
  
 n = 정렬된 드롭 목록  
  
 1 = DDX 삽입 목록 헤드에 추가 해야 하는 경우 (기본값은 꼬리에 추가 됨)이 옵션이 사용 '제어' 속성을 전송 하는 DDX 루틴입니다.  
  
 \<vb 키 >  
 이 필드는 (VBX 컨트롤은 32 비트 제품에서 지원 되지 않습니다) VBX 컨트롤에 대 한 16 비트 제품에만 사용  
  
 \<프롬프트 >  
 속성 콤보 상자 (따옴표 제외)에 배치 하는 문자열  
  
 \<type>  
 헤더 파일에 내보낼 수 형식에 대 한 단일 식별자입니다. 위의 예제와 DDX_Time CTime로 설정이 것입니다.  
  
 \<vb 키 >  
 이 버전에서는 사용 되지 않으며 수  
  
 \<initValue >  
 초기 값-0 또는 공백입니다. 빈 경우 초기화 선이 없습니다 구현 파일의 //{{AFX_DATA_INIT 섹션에 기록 됩니다. C + + 개체에 빈 항목을 사용 해야 (같은 `CString`, `CTime`등) 올바른 초기화를 보장 하는 생성자가 있는 경우입니다.  
  
 < DDX_Proc >  
 DDX_ 프로시저에 대 한 단일 식별자입니다. C + + 함수 이름은 "DDX_"로 시작 해야 하지만 < DDX_Proc > 식별자에 "DDX_"를 포함 하지 않습니다. 위의 예에서 < DDX_Proc > 식별자 시간 것입니다. 클래스 마법사 함수 호출에는 구현 파일을 작성 하는 경우는 {{AFX_DATA_MAP 섹션 추가이 이름은 하기 DDX_, 따라서 DDX_Time에 도착 합니다.  
  
 \<주석 >  
 이 DDX 사용 하 여 변수 대화 상자에 표시 되는 설명입니다. 여기에서 그리고 일반적으로 항목을 제공 하려는 DDX/DDV 쌍으로 수행 되는 작업을 설명 하는 모든 텍스트를 배치 합니다.  
  
 < DDV_Proc >  
 항목의 DDV 부분은 선택 사항입니다. 일부 DDX 루틴은 해당 DDV 루틴입니다. 전송의 필수적인 부분으로 유효성 검사 단계를 포함 하는 편리한 방법을 하는 경우가 많습니다. 이 경우 종종는 DDV 루틴 매개 변수를 요구 하지 않는 경우 클래스 마법사가 매개 변수 없이 DDV 루틴을 지원 하지 않으므로 합니다.  
  
 \<arg >  
 DDV_ 프로시저에 대 한 단일 식별자입니다. C + + 함수 이름을 "DDV_"로 시작 해야 하지만 < DDX_Proc > 식별자에 "DDX_"를 포함 하지 마십시오.  
  
 1 개 또는 2 DDV args 옵니다.  
  
 \<promptX >  
 항목 편집 (엑셀 러 레이 터에 대 한 &) 위에 배치 하는 문자열  
  
 \<fmtX >  
 arg 종류 중 하나에 대 한 형식 문자  
  
 d = int  
  
 u = 서명 되지 않은  
  
 D = long int (즉, long)  
  
 U = 긴 서명 되지 않은 (즉, DWORD)  
  
 f = float  
  
 F = double  
  
 s = 문자열  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

