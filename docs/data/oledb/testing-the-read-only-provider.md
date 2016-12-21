---
title: "읽기 전용 공급자 테스트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자, 호출"
  - "OLE DB 공급자, 테스트"
  - "공급자 테스트"
  - "테스트, OLE DB 공급자"
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 읽기 전용 공급자 테스트
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

공급자를 테스트하려면 소비자가 있어야 합니다.  소비자가 공급자와 조화되면 테스트에 도움이 됩니다.  OLE DB 소비자 템플릿은 OLE DB에 사용되는 씬 래퍼로 공급자 COM 개체와 잘 조화됩니다.  소스에 소비자 템플릿이 제공되므로 소비자 템플릿을 사용하여 쉽게 공급자를 디버깅할 수 있습니다.  뿐만 아니라 소비자 템플릿을 사용하면 소비자 응용 프로그램을 쉽고 빠르게 만들 수 있습니다.  
  
 이 항목의 예제에서는 테스트 소비자에 대해 기본 MFC 응용 프로그램 마법사 응용 프로그램을 만듭니다.  테스트 응용 프로그램은 OLE DB 소비자 템플릿 코드가 추가된 간단한 대화 상자입니다.  
  
### 테스트 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  프로젝트 형식 창에서 **Visual C\+\+ 프로젝트** 폴더를 선택합니다.  템플릿 창에서 **MFC 응용 프로그램**을 선택합니다.  
  
3.  프로젝트 이름으로 **TestProv**를 입력하고 **확인**을 클릭합니다.  
  
     MFC 응용 프로그램 마법사가 나타납니다.  
  
4.  **응용 프로그램 종류** 페이지에서 **대화 상자 기반**을 선택합니다.  
  
5.  **고급 기능** 페이지에서 **자동화**를 선택하고 **마침**을 클릭합니다.  
  
> [!NOTE]
>  **CTestProvApp::InitInstance**에 **CoInitialize**를 추가할 경우에는 응용 프로그램에 자동화 지원이 필요하지 않습니다.  
  
 리소스 뷰에서 TestProv 대화 상자\(IDD\_TESTPROV\_DIALOG\)를 선택하여 대화 상자를 보고 편집할 수 있습니다.  대화 상자에 행 집합의 각 문자열에 대해 하나씩 두 목록 상자를 넣습니다.  Alt\+Enter를 누른 채 목록 상자를 선택하고 **스타일** 탭을 클릭한 다음 **정렬** 확인란 선택을 취소하여 두 목록 상자의 정렬 속성을 해제합니다.  파일을 페치하기 위한 **실행** 단추도 대화 상자에 넣습니다.  완성된 TestProv 대화 상자에는 "String 1"과 "String 2"라는 두 목록 상자와 **확인**, **취소**, **실행** 단추가 있어야 합니다.  
  
 대화 상자 클래스의 헤더 파일\(이 경우 TestProvDlg.h\)을 열고  클래스 선언 바깥 부분에 다음 코드를 추가합니다.  
  
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
  
 이 코드는 행 집합에 나타날 열을 정의하는 사용자 레코드를 나타냅니다.  클라이언트가 **IAccessor::CreateAccessor**를 호출하면 이러한 항목을 사용하여 바인딩할 열을 지정합니다.  또한 OLE DB 소비자 템플릿을 사용하여 열을 동적으로 바인딩할 수 있습니다.  COLUMN\_ENTRY 매크로는 PROVIDER\_COLUMN\_ENTRY 매크로의 클라이언트 쪽 버전입니다.  두 COLUMN\_ENTRY 매크로는 두 문자열의 서수, 형식, 길이 및 데이터 멤버를 지정합니다.  
  
 Ctrl 키를 누르고 **실행** 단추를 두 번 클릭하여 **실행** 단추에 대한 처리기 함수를 추가한 다음  이 함수에 다음 코드를 넣습니다.  
  
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
  
 `CCommand`, `CDataSource` 및 `CSession` 클래스는 모두 OLE DB 소비자 템플릿에 속합니다.  이러한 각 클래스는 공급자에서 COM 개체를 모방합니다.  `CCommand` 개체는 헤더 파일에 선언된 `CProvider` 클래스를 템플릿 매개 변수로 사용합니다.  `CProvider` 매개 변수는 공급자의 데이터에 액세스하기 위해 사용할 바인딩을 나타냅니다.  Here is the `Open` code for the data source, session, and command:  
  
```  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 각 클래스를 열기 위한 위 코드는 공급자에 각 COM 개체를 만듭니다.  공급자가 있는 위치를 찾으려면 공급자의 ProgID를 사용합니다.  시스템 레지스트리에서 ProgID를 찾거나 MyProvider.rgs 파일\(공급자 디렉터리를 열고 ProgID 키 검색\)에서 ProgID를 찾을 수 있습니다.  
  
 MyProv 샘플에는 MyData.txt 파일이 포함되어 있습니다.  직접 파일을 만들려면 편집기를 사용하여 각 문자열 사이에 Enter 키를 눌러 짝수 개수의 문자열을 입력합니다.  파일을 이동한 경우에는 경로 이름을 변경합니다.  
  
 `table.Open` 줄에 "c:\\\\samples\\\\myprov\\\\MyData.txt" 문자열을 전달합니다.  `Open` 호출 단계에 이르면 이 문자열이 공급자의 `SetCommandText` 메서드로 전달된 것을 볼 수 있습니다.  `ICommandText::Execute` 메서드가 이 문자열을 사용했음에 주목하십시오.  
  
 데이터를 페치하려면 테이블에 대해 `MoveNext`를 호출합니다.  `MoveNext`는 **IRowset::GetNextRows**, `GetRowCount` 및 `GetData` 함수를 호출합니다.  더 이상 행이 없으면, 즉 행 집합의 현재 위치가 `GetRowCount`보다 크면 루프가 종료됩니다.  
  
```  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 더 이상 행이 없으면 공급자가 **DB\_S\_ENDOFROWSET**을 반환합니다.  **DB\_S\_ENDOFROWSET** 값은 오류가 아닙니다.  데이터 페치 루프를 취소하고 SUCCEEDED 매크로를 사용하지 않으려면 항상 `S_OK`를 확인해야 합니다.  
  
 이제 프로그램을 빌드하고 테스트할 수 있습니다.  
  
## 참고 항목  
 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)