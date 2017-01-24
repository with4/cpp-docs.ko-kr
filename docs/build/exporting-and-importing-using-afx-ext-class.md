---
title: "AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기 | Microsoft Docs"
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
  - "afx_ext_class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_EXT_CLASS 매크로"
  - "실행 파일[C++], 클래스 가져오기"
  - "클래스 내보내기[C++]"
  - "DLL 내보내기[C++], AFX_EXT_CLASS 매크로"
  - "확장 DLL[C++], 클래스 내보내기"
  - "importing DLL[C++]"
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[확장 DLL](../build/extension-dlls-overview.md)은 **AFX\_EXT\_CLASS** 매크로를 사용하여 클래스를 내보내고, 확장 DLL에 링크하는 실행 파일은 이 매크로를 사용하여 클래스를 가져옵니다.  **AFX\_EXT\_CLASS** 매크로를 사용하는 경우에는 확장 DLL을 빌드하는 데 사용되는 것과 동일한 헤더 파일을 해당 DLL을 링크하는 실행 파일에도 사용할 수 있습니다.  
  
 DLL에 대한 헤더 파일에서 다음과 같이 클래스 선언에 **AFX\_EXT\_CLASS** 키워드를 추가합니다.  
  
```  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
 이 매크로는 전처리기 기호인 **\_AFXDLL** 및 `_AFXEXT`가 정의될 때 MFC에서 **\_\_declspec\(dllexport\)**으로 정의됩니다.  그러나 **\_AFXDLL**은 정의되고 `_AFXEXT`가 정의되지 않으면 이 매크로는 **\_\_declspec\(dllimport\)**으로 정의됩니다.  전처리기 기호 **\_AFXDLL**이 정의된 경우 이 기호는 대상 실행 파일\(DLL 또는 응용 프로그램\)에서 MFC의 공유 버전을 사용하고 있음을 나타냅니다.  **\_AFXDLL**과 `_AFXEXT`가 모두 정의된 경우에는 대상 실행 파일이 확장 DLL임을 나타냅니다.  
  
 **AFX\_EXT\_CLASS**는 확장 DLL에서 내보낼 때 **\_\_declspec\(dllexport\)**으로 정의되기 때문에 해당 클래스의 모든 기호에 대한 데코레이팅된 이름을 .def 파일에 포함하지 않고도 전체 클래스를 내보낼 수 있습니다.  이 방법은 MFC 샘플 [DLLHUSK](http://msdn.microsoft.com/ko-kr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90)에서 사용됩니다.  
  
 이 방법을 사용할 경우 .def 파일과 해당 클래스의 모든 데코레이팅된 이름을 만들지 않아도 되지만, .def 파일을 만들면 이 이름을 서수로 내보낼 수 있으므로 좀 더 효율적입니다.  .def 파일을 사용하여 내보내려면 헤더 파일의 처음과 끝 부분에 다음 코드를 추가합니다.  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  인라인 함수를 내보낼 때에는 버전 충돌이 발생할 수 있으므로 주의해야 합니다.  인라인 함수는 응용 프로그램 코드로 확장됩니다. 따라서 나중에 이 함수를 다시 쓰는 경우 해당 응용 프로그램을 다시 컴파일해야만 함수가 업데이트됩니다.  반면, 일반적인 DLL 함수는 해당 함수를 사용하는 응용 프로그램을 다시 빌드하지 않아도 업데이트됩니다.  
  
## 클래스의 개별 멤버 내보내기  
 때로는 클래스의 개별 멤버를 내보내려는 경우가 있습니다.  예를 들어, `CDialog` 파생 클래스를 내보내는 경우 해당 생성자 및 `DoModal` 호출만 내보내야 하는 경우가 있습니다.  이런 경우에는 내보내야 할 개별 멤버에 **AFX\_EXT\_CLASS**를 사용하면 됩니다.  
  
 예를 들면 다음과 같습니다.  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
   AFX_EXT_CLASS CExampleDialog();  
   AFX_EXT_CLASS int DoModal();  
   ...  
   // rest of class definition  
   ...  
};  
```  
  
 해당 클래스의 모든 멤버를 더 이상 내보내지 않으므로 MFC 매크로의 작동 방식으로 인한 추가 문제가 발생할 수 있습니다.  MFC의 일부 도우미 매크로에서는 실제로 데이터 멤버를 선언하거나 정의합니다.  따라서 이러한 데이터 멤버도 DLL에서 내보내야 합니다.  
  
 예를 들어, 확장 DLL을 빌드할 때에는 다음과 같이 `DECLARE_DYNAMIC` 매크로가 정의됩니다.  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
 static `AFX_DATA`로 시작하는 줄은 클래스 내부의 정적 개체를 선언합니다.  이 클래스를 올바르게 내보내고 클라이언트 실행 파일에서 런타임 정보에 액세스하려면 이 정적 개체를 내보내야 합니다.  정적 개체는 `AFX_DATA` 한정자를 사용하여 선언되기 때문에 이 `AFX_DATA`를 DLL 빌드 시에는 **\_\_declspec\(dllexport\)**으로 정의하고 클라이언트 실행 파일 빌드 시에는 **\_\_declspec\(dllimport\)**으로 정의합니다.  **AFX\_EXT\_CLASS**는 이미 이러한 방식으로 정의되어 있으므로 클래스 정의 부분에서 `AFX_DATA`를 **AFX\_EXT\_CLASS**와 동일하게 다시 정의합니다.  
  
 예를 들면 다음과 같습니다.  
  
```  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
  
class CExampleView : public CView  
{  
   DECLARE_DYNAMIC()  
   // ... class definition ...  
};  
  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
 MFC는 해당 매크로 내에서 정의하는 데이터 항목에 대해 항상 `AFX_DATA` 기호를 사용하므로 이 기술은 이러한 모든 시나리오에 적용됩니다.  예를 들어, 이 기술은 `DECLARE_MESSAGE_MAP`에도 적용됩니다.  
  
> [!NOTE]
>  클래스에서 선택한 멤버만 내보내는 것이 아니라 전체 클래스를 내보내는 경우에는 정적 데이터 멤버가 자동으로 내보내집니다.  
  
### 수행할 작업  
  
-   [.def 파일을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\)을 사용하여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C\+\+ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C 함수를 C 또는 C\+\+ 언어 실행 파일에서 사용할 수 있도록 내보내기](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\)을 사용하여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
### 추가 정보  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
-   [인라인 함수 가져오기 및 내보내기](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
## 참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)