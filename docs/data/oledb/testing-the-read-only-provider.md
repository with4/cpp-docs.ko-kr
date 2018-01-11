---
title: "읽기 전용 공급자 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 438ab42a7f0f12379621a591f3b0b1eeb5930afd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="testing-the-read-only-provider"></a>읽기 전용 공급자 테스트
공급자를 테스트 하려면 소비자가 있어야 합니다. 공급자와 소비자 수와 일치 하는 경우 도움이 됩니다. OLE DB 소비자 템플릿은 OLE DB에 대 한 씬 래퍼 있으며 공급자 COM 개체와 일치 합니다. 소스는 소비자 템플릿과 함께 제공 되, 때문에 이러한 공급자를 디버깅할 쉽습니다. 소비자 템플릿은 소비자 응용 프로그램을 개발 하는 매우 작고 빠른 방법입니다.  
  
 이 항목의 예제는 테스트 소비자에 대 한 기본 MFC 응용 프로그램 마법사 응용 프로그램을 만듭니다. 테스트 응용 프로그램은 OLE DB 소비자 템플릿 코드가 추가 된 간단한 대화 상자.  
  
### <a name="to-create-the-test-application"></a>테스트 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  프로젝트 형식 창에서 선택 된 **Visual c + + 프로젝트** 폴더입니다. 템플릿 창에서 선택 **MFC 응용 프로그램**합니다.  
  
3.  프로젝트 이름에 대 한 입력 **TestProv**, 클릭 하 고 **확인**합니다.  
  
     MFC 응용 프로그램 마법사가 나타납니다.  
  
4.  에 **응용 프로그램 종류** 페이지에서 **대화 상자 기반**합니다.  
  
5.  에 **고급 기능** 페이지에서 **자동화**, 클릭 하 고 **마침**합니다.  
  
> [!NOTE]
>  추가 하는 경우 응용 프로그램 자동화 지원이 필요로 하지 않는 **CoInitialize** 에 **CTestProvApp::InitInstance**합니다.  
  
 확인 및 리소스 뷰에서 선택 하 여 TestProv 대화 상자 (IDD_TESTPROV_DIALOG)를 편집할 수 있습니다. 대화 상자에는 행 집합의 각 문자열에 대해 하나씩 두 개의 목록 상자를 배치 합니다. ALT + Enter를 눌러 목록 상자를 선택 하 고, 클릭 하면 목록 상자 둘 다에 대해 정렬 속성이 해제는 **스타일** 탭을 선택 취소 된 **정렬** 확인란 합니다. 또한 배치는 **실행** 파일을 대화 상자에서 단추입니다. 완성 된 TestProv 대화 상자에 "문자열 1" 및 "2 문자열"를 각각;로 표시 된 두 개의 목록 상자 있어야 합니다. 또한 **확인**, **취소**, 및 **실행** 단추입니다.  
  
 (이 case TestProvDlg.h)에서 대화 상자 클래스에 대 한 헤더 파일을 엽니다. 클래스 선언) (외부 헤더 파일에 다음 코드를 추가 합니다.  
  
```  
////////////////////////////////////////////////////////////////////////  
// TestProvDlg.h  
  
class CProvider   
{  
// Attributes  
public:  
   char   szField1[16];  
   char   szField2[16];  
  
   // Binding Maps  
BEGIN_COLUMN_MAP(CProvider)  
   COLUMN_ENTRY(1, szField1)  
   COLUMN_ENTRY(2, szField2)  
END_COLUMN_MAP()  
};  
```  
  
 코드 행 집합에 나타날 하는 열을 정의 하는 사용자 레코드를 나타냅니다. 클라이언트 호출 하는 경우 **iaccessor:: Createaccessor**, 이러한 항목을 사용 하 여 바인딩할 열을 지정할 수 있습니다. OLE DB 소비자 템플릿 열을 동적으로 바인딩할 수도 있습니다. COLUMN_ENTRY 매크로 PROVIDER_COLUMN_ENTRY 매크로의 클라이언트 쪽 버전입니다. 두 COLUMN_ENTRY 매크로 서 수, 두 개의 문자열에 대 한 형식, 길이 및 데이터 멤버를 지정 합니다.  
  
 처리기 함수에 대 한 추가 **실행** CTRL 키를 누르고 두 번 클릭 하면 단추는 **실행** 단추입니다. 함수에 다음 코드를 배치 합니다.  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
      return;  
  
   while (table.MoveNext() == S_OK)  
   {  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
   }  
}  
```  
  
 `CCommand`, `CDataSource`, 및 `CSession` OLE DB 소비자 템플릿에 속한 모든 클래스입니다. 각 클래스는 공급자에서 COM 개체를 모방합니다. `CCommand` 개체는 `CProvider` 템플릿 매개 변수로 헤더 파일에 선언 된 클래스입니다. `CProvider` 매개 변수는 공급자에서 데이터에 액세스 하는 데 사용할 수 있는 바인딩을 나타냅니다. 다음은 `Open` 데이터 원본, 세션 및 명령에 대 한 코드:  
  
```  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 각각의 클래스를 열려는 행 공급자에서 각 COM 개체를 만듭니다. 공급자를 찾을 공급자의 ProgID를 사용 합니다. 시스템 레지스트리에서 또는 MyProvider.rgs 파일을 보면 ProgID를 얻을 수 있습니다 (공급자의 디렉터리 및 ProgID 키에 대 한 검색 열기).  
  
 MyData.txt 파일 MyProv 샘플에 포함 됩니다. 사용자의 파일을 만들려면 편집기를 사용 하 고 enter 키를 눌러 각 문자열 사이 문자열의 수는 짝수를 입력 합니다. 파일을 이동 하는 경우 경로 이름을 변경 합니다.  
  
 문자열에 전달 "c:\\\samples\\\myprov\\\MyData.txt"에서 `table.Open` 선입니다. 경우에 `Open` 호출 표시이 문자열에 전달 되는 `SetCommandText` 공급자의 메서드. `ICommandText::Execute` 메서드는이 문자열을 사용 합니다.  
  
 데이터를 페치 하려면 호출 `MoveNext` 테이블에 있습니다. `MoveNext`호출 된 **irowset:: Getnextrows**, `GetRowCount`, 및 `GetData` 함수입니다. 행이 더 이상 없는 경우 (즉, 행 집합의 현재 위치 보다 큽니다 `GetRowCount`), 루프가 종료 됩니다.  
  
```  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 더 많은 행이 없는 경우 공급자 반환 **DB_S_ENDOFROWSET**합니다. **DB_S_ENDOFROWSET** 값은 오류가 아닙니다. 에 대해 항상 확인 해야 `S_OK` 데이터 인출 루프를 취소 및 SUCCEEDED 매크로 사용 하지 않습니다.  
  
 이제을 빌드 및 프로그램을 테스트할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)