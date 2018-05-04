---
title: AFX_EXT_CLASS를 사용 하 여 가져오기 및 내보내기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- afx_ext_class
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6cc853c66afae72d6e426d800c0443ab206ab20
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-and-importing-using-afxextclass"></a>AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기  
  
[MFC 확장 Dll](../build/extension-dlls-overview.md) 매크로 사용 하 여 **AFX_EXT_CLASS** 내보낼 클래스, 클래스를 가져오려면 매크로 사용 하는 MFC 확장 DLL에 연결 된 실행 합니다. 와 **AFX_EXT_CLASS** 매크로, MFC 확장 DLL DLL에 연결 하는 실행 파일과 함께 사용할 수 있습니다를 작성 하는 데 사용 되는 동일한 헤더 파일입니다.  
  
 DLL의 헤더 파일에 추가 된 **AFX_EXT_CLASS** 키워드 다음과 같이 클래스의 선언에:  
  
```cpp  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
이 매크로으로 MFC에 의해 정의 됩니다 `__declspec(dllexport)` 때 전처리기 기호 `_AFXDLL` 및 `_AFXEXT` 정의 됩니다. 매크로로 정의 됩니다 `__declspec(dllimport)` 때 `_AFXDLL` 정의 및 `_AFXEXT` 정의 되어 있지 않습니다. 전처리기 기호를 정의 하는 경우 `_AFXDLL` 공유 버전의 MFC는 대상 실행 파일 (DLL 또는 응용 프로그램)에서 사용 되 고 됨을 나타냅니다. 때 둘 다 `_AFXDLL` 및 `_AFXEXT` 되는 대상 실행 파일은 MFC 확장 DLL 임을 나타냅니다 정의 합니다.  
  
때문에 `AFX_EXT_CLASS` 로 정의 `__declspec(dllexport)` MFC 확장 DLL 내보낼 때 모든 해당 클래스의 기호에 대 한 트 데코 레이 된 이름이.def 파일에 배치 하지 않고 전체 클래스를 내보낼 수 있습니다.  
  
이 메서드를 사용 하 여.def 파일 및 클래스에 대 한 트 데코 레이 된 이름의 모든 만들기를 방지 하지만.def 파일을 만드는 더 효율적입니다 이름은 서 수로 내보낼 수 있으므로. 내보내기의.def 파일 메서드를 사용 하려면 헤더 파일의 시작과 끝에 다음 코드를 추가 합니다.  
  
```cpp  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  인라인 함수를 내보낼 때 주의 때문일 버전 충돌 가능성을 만들 수 있습니다. 응용 프로그램 코드;으로 인라인 함수 확장 따라서 함수를 나중에 다시 작성할 때이 업데이트 되지 않습니다 응용 프로그램 자체를 다시 컴파일할 하지 않는 한 합니다. 일반적으로 DLL 함수를 사용 하는 응용 프로그램을 다시 작성 하지 않고 업데이트할 수 있습니다.  
  
## <a name="exporting-individual-members-in-a-class"></a>개별 멤버 클래스에서 내보내기  
  
클래스의 개별 멤버를 내보내려면 하는 경우가 있습니다. 예를 들어, 내보내는 경우는 `CDialog`-파생 클래스 생성자는 내보낼 하기만 하면 및 `DoModal` 호출 합니다. 사용할 수 있습니다 `AFX_EXT_CLASS` 내보내야 하는 개별 멤버에 있습니다.  
  
예를 들어:  
  
```cpp  
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
  
클래스의 모든 멤버를 더 이상 내보낼 때문에 발생할 수 없습니다 다른 문제는 방식으로 인해 MFC 매크로 작동 합니다. 일부 MFC의 도우미 매크로 실제로 선언 하거나 데이터 멤버를 정의 합니다. 따라서 이러한 데이터 멤버 DLL에서 내보내야 합니다.  
  
예를 들어는 `DECLARE_DYNAMIC` 매크로 MFC 확장 DLL을 빌드할 때 다음과 같이 정의 됩니다.  
  
```cpp  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
정적 행이 있는 시작 하는 줄 `AFX_DATA` 클래스 내부에서 정적 개체를 선언 합니다. 이 클래스를 올바르게 내보내고 클라이언트 실행 파일에서 런타임 정보에 액세스, 정적이 개체를 내보내야 합니다. 정적 개체는 한정자로 선언 되었으므로 `AFX_DATA`를 정의 해야 `AFX_DATA` 되도록 `__declspec(dllexport)` DLL을 빌드할 때로 정의 하 고 `__declspec(dllimport)` 클라이언트를 실행 파일을 만들 때. 때문에 `AFX_EXT_CLASS` 이미 정의 되어 이러한 방식으로 하기만 하면 다시 정의할 `AFX_DATA` 와 동일 하 게 `AFX_EXT_CLASS` 주위 클래스 정의 합니다.  
  
예를 들어:  
  
```cpp  
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
  
MFC에서 항상 사용 하기 때문에 `AFX_DATA` 해당 매크로 내에서 정의 하는 데이터 항목에는 기호가 이러한 모든 시나리오에이 기술 작동 합니다. 예를 들어에 대해서 작동 `DECLARE_MESSAGE_MAP`합니다.  
  
> [!NOTE]
>  클래스의 선택한 멤버 보다는 전체 클래스를 내보내는 경우 정적 데이터 멤버가 자동으로 내보내집니다.  
  
### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [.Def 파일을 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec (dllexport)를 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C 언어 실행 파일에서 사용 하기 위해 c + + 함수 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C 또는 c + + 언어 실행 파일에서 사용 하기 위해 내보내기 C 함수](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec (dllimport)을 사용 하 여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
-   [가져오기 및 내보내기 인라인 함수](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
## <a name="see-also"></a>참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)