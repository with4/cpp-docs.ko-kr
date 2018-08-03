---
title: 내보내기 | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- EXPORTS
dev_langs:
- C++
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c642a623e76a9e1344a90efd4f0a47ad195c553e
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322191"
---
# <a name="exports"></a>EXPORTS

함수 또는 데이터의 내보낸 이름이나 서수를 지정하는 하나 이상의 내보내기 정의 섹션에 대해 소개합니다. 각 정의는 별도의 줄에 있어야 합니다.  
  
```DEF  
EXPORTS  
   definition  
```  
  
## <a name="remarks"></a>설명  

첫 번째 *정의* 와 동일한 줄에 있을 수 있습니다는 `EXPORTS` 키워드 또는 후속 줄. .DEF 파일에는 `EXPORTS` 문이 한 개 이상 있을 수 있습니다.  
  
내보내기에 대 한 구문을 *정의* 됩니다.  
  
```DEF
entryname[=internal_name|other_module.another_exported_name] [@Ordinal [NONAME]] [[PRIVATE] | [DATA]]
```

*entryname* 내보내려는 함수 또는 변수 이름입니다. 이는 필수입니다. 내보내는 이름이 DLL의 이름과 다를 경우 내보내기의 이름을 DLL에서 사용 하 여 지정할 *internal_name*합니다. 예를 들어 DLL이 함수 `func1`을 내보내고 호출자가 이 함수를 `func2`로 사용하도록 하려는 경우 다음과 같이 지정할 수 있습니다.

```DEF
EXPORTS
   func2=func1
```

다른 모듈에서 내보내는 이름이 인 경우 내보내기의 이름을 DLL에서 사용 하 여 지정할 *other_module.exported_name*합니다. 예를 들어 DLL이 함수 `other_module.func1`을 내보내고 호출자가 이 함수를 `func2`로 사용하도록 하려는 경우 다음과 같이 지정할 수 있습니다.

```DEF
EXPORTS
   func2=other_module.func1
```

C + + 함수에 대 한 이름 데코레이션을 사용 하는 Visual c + + 컴파일러, 때문에 데코레이팅된 이름을 internal_name 사용 하거나 소스 코드에서 extern "C"를 사용 하 여 내보낸된 함수를 정의 합니다. 컴파일러에는 또한 C 함수를 사용 하 여 데코 레이트 합니다 [__stdcall](../../cpp/stdcall.md) 호출 규칙에 밑줄 (_) 접두사와 접미사로 at 기호 (@) 뒤에 바이트 수 (10 진수) 인수 목록의 합니다.  
  
컴파일러에서 생성 된 데코레이팅된 이름을 찾으려면 사용 합니다 [DUMPBIN](../../build/reference/dumpbin-reference.md) 도구 또는 링커 [/map](../../build/reference/map-generate-mapfile.md) 옵션입니다. 데코레이팅된 이름은 컴파일러별로 다릅니다. .DEF 파일의 데코레이팅된 이름을 내보내는 경우 DLL에 연결된 실행 파일도 동일한 버전의 컴파일러를 사용하여 빌드해야 합니다. 그래야 호출자의 데코레이팅된 이름이 .DEF 파일의 내보낸 이름과 일치하게 됩니다.  
  
를 사용할 수 있습니다*서* 숫자 및 함수 이름이 아니라 DLL의 내보내기 테이블로 이동 됩니다 지정 합니다. 많은 Windows DLL은 서수를 내보내 레거시 코드를 지원합니다. Windows DLL의 크기를 최소화할 수 있기 때문에 16비트 Windows 코드에서는 서수를 사용하는 것이 일반적입니다. DLL 클라이언트에서 레거시 지원에 서수를 사용할 필요가 없는 경우 서수별 함수를 내보내지 않는 것이 좋습니다. .LIB 파일에는 서수와 함수 간의 매핑이 포함되므로 DLL을 사용하는 프로젝트에서 일반적으로 하는 것처럼 함수 이름을 사용할 수 있습니다.  
  
선택적 `NONAME` 키워드를 사용하여 서수로만 내보낼 수 있고 결과 DLL에서 내보내기 테이블의 크기를 줄일 수 있습니다. 그러나 사용 하려는 경우 [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) DLL에서 알고 있어야 합니다 서 수 있으므로 이름이 유효 하지 않게 됩니다.  
  
선택적 키워드인 `PRIVATE` 방지 *entryname* 링크에 의해 생성 된 가져오기 라이브러리에 포함 되지 합니다. 이는 LINK에서도 생성한 이미지에서 내보내기에 영향을 미치지 않습니다.  
  
선택적 키워드 `DATA`는 내보내기가 코드가 아니라 데이터가 되도록 지원합니다. 아래 예제는 `exported_global` 데이터 변수를 내보낼 수 있는 방법을 보여줍니다.  
  
```DEF  
EXPORTS  
   exported_global DATA  
```  
  
다음은 정의를 내보내는 4가지 방법으로 권장 순서대로 나열되었습니다.  
  
1.  합니다 [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) 소스 코드의 키워드  
  
2.  .DEF 파일의 `EXPORTS` 문  
  
3.  [/내보내기](../../build/reference/export-exports-a-function.md) LINK 명령의 사양  
  
4.  A [주석](../../preprocessor/comment-c-cpp.md) 폼의 소스 코드에 지시문 `#pragma comment(linker, "/export: definition ")`  
  
4가지 메서드 모두 동일한 프로그램에서 사용할 수 있습니다. LINK가 내보내기를 포함하는 프로그램을 빌드하는 경우 빌드에서 .EXP 파일을 사용하지 않는다면 가져오기 라이브러리도 만들게 됩니다.  
  
다음은 EXPORTS 섹션의 예입니다.  
  
```DEF  
EXPORTS  
   DllCanUnloadNow      @1          PRIVATE  
   DllWindowName = WindowName       DATA  
   DllGetClassObject    @4 NONAME   PRIVATE  
   DllRegisterServer    @7  
   DllUnregisterServer  
```  
  
.DEF 파일을 사용하여 DLL에서 변수를 내보낸 경우 변수에 대해 `__declspec(dllexport)`을 지정할 필요가 없습니다. 그러나 DLL을 사용하는 모든 파일에서는 데이터 선언 시 `__declspec(dllimport)`을 계속해서 사용해야 합니다.  
  
## <a name="see-also"></a>참고자료

[모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)
