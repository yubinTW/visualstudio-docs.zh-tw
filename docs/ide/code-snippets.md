---
title: "程式碼片段 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- surround with
- code snippets
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 514408ff2dbbde12d243a1458c380a2e17b516cc
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2018
---
# <a name="code-snippets"></a>程式碼片段

程式碼片段是可重複使用的程式碼之小型區塊，可以使用操作功能表命令或快速鍵的組合在程式碼檔案中插入。 其常包含常用的程式碼區塊，例如 `try-finally` 或 `if-else` 區塊，但可以用來插入整個類別或方法。

程式碼片段可使用的語言包括 C#、C++、Visual Basic、XML 和 T-SQL 等等。 若要檢視所有已安裝可用的程式碼片段語言，請從 Visual Studio 功能表的 [工具] 開啟 [程式碼片段管理員]，並從頂端下拉功能表中選擇語言。

![[程式碼片段管理員] 對話方塊](media/code-snippets-manager.png)

程式碼片段可用下列一般方式存取：

- 在功能表列上選擇 [編輯] > [IntelliSense] > [插入程式碼片段...]

- 以滑鼠右鍵按一下內容功能表，或是從程式碼編輯器中，選擇 [片段] > [插入程式碼片段...]

- 或者，您也可以從鍵盤按 **Ctrl**+**K**+**X**

## <a name="expansion-snippets-and-surround-with-snippets"></a>擴充程式碼片段和範圍陳述式程式碼片段

在 Visual Studio 中，有兩種類型的程式碼片段：擴充程式碼片段，這會在指定的插入點加入，而且可能會取代程式碼片段捷徑，以及範圍陳述式程式碼片段 (僅限 C# 和 C++)，可在選取的程式碼區塊前後加入。

擴充程式碼片段的範例：在 C# 中，捷徑 tryf 可用來插入 try-finally 區塊：

```csharp
try
{

}
finally
{

}
```

插入此程式碼片段的方式，是在程式碼視窗的操作功能表中依序按一下 [插入程式碼片段] 和 [Visual C#]，並鍵入 `tryf`，然後按 **TAB**。或者，您可以輸入 `tryf` 並按 **TAB** 兩次。

範圍陳述式程式碼片段的範例：在 C++中，捷徑 `if` 可用作插入程式碼片段或範圍陳述式程式碼片段。 如果您選取一行程式碼 (例如 `return FALSE;`)，然後選擇 [Surround With] \(範圍陳述式\) > [if]，程式碼片段隨即在此行周圍展開：

```cpp
if (true)
{
    return FALSE;
}
```

## <a name="snippet-replacement-parameters"></a>程式碼片段取代參數

程式碼片段可以包含取代參數，這些都是您必須取代的預留位置，以符合您要撰寫的精確程式碼。 在上述範例中，`true` 是取代參數，您必須以適當的條件取代。 在此程式碼片段中同一個取代參數的每個執行個體都要重複這項您所進行的取代。

例如，在 Visual Basic 中有會插入屬性的程式碼片段。 若要插入程式碼片段，請在 Visual Basic 程式碼檔中以滑鼠右鍵按一下，或是從內容功能表中選擇 [片段...] > [插入程式碼片段]。 然後，選擇 [程式碼模式] > [屬性、程序、事件] > [定義屬性]。

![定義屬性的程式碼片段功能表](media/code-snippets-vb-property.png)

以下是已插入的程式碼：

```vb
Private newPropertyValue As String
Public Property NewProperty() As String
    Get
        Return newPropertyValue
    End Get
    Set(ByVal value As String)
        newPropertyValue = value
    End Set
End Property
```

如果您變更 `newPropertyValue` 為 `m_property`，則會變更每個 `newPropertyValue` 的執行個體。 如果您在屬性宣告中變更 `String` 為 `Int`，則已設定方法中的值也會變更為 `Int`。

## <a name="see-also"></a>另請參閱

[逐步解說：建立程式碼片段](../ide/walkthrough-creating-a-code-snippet.md)  
[如何：散發程式碼片段](../ide/how-to-distribute-code-snippets.md)  
[使用程式碼片段的最佳做法](../ide/best-practices-for-using-code-snippets.md)  
[針對程式碼片段進行疑難排解](../ide/troubleshooting-snippets.md)  
[C# 程式碼片段](../ide/visual-csharp-code-snippets.md)  
[Visual C++ 程式碼片段](../ide/visual-cpp-code-snippets.md)  
[程式碼片段結構描述參考](../ide/code-snippets-schema-reference.md)