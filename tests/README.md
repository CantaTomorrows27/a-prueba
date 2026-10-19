# Adding a listening test

Put one folder per test under `tests/`. A test folder should contain `test.json`, five audio recordings, and twenty picture files (four choices per question). PNG and JPG images are supported; MP3 audio is recommended.

Example:

```text
tests/
  index.json
  mi-prueba/
    test.json
    question-1.mp3
    question-1-a.png
    question-1-b.png
    question-1-c.png
    question-1-d.png
    ...
```

The app loads the test list from `tests/index.json`. Each entry has a display title and the path to its `test.json`:

```json
[
  {"title":"Mi prueba", "file":"mi-prueba/test.json"}
]
```

Each test file has five questions. For each question, set `audio` to the recording filename, `answer` to the ID of the correct choice, and `choices` to exactly four choices. Set each choice's `image` to its image filename. Keep the `id` values distinct within that question. Example:

```json
{
  "id":"mi-prueba",
  "title":"Mi prueba",
  "questions":[
    {
      "audio":"question-1.mp3",
      "answer":"opcion-c",
      "choices":[
        {"id":"opcion-a", "label":"Opción A", "image":"question-1-a.png"},
        {"id":"opcion-b", "label":"Opción B", "image":"question-1-b.png"},
        {"id":"opcion-c", "label":"Opción C", "image":"question-1-c.png"},
        {"id":"opcion-d", "label":"Opción D", "image":"question-1-d.png"}
      ]
    }
  ]
}
```

Repeat that question entry five times. The sample test is a complete working example. When you send a folder with your media and `answer-key.txt`, I can prepare the JSON files and add it to the list for you. New tests added to a GitHub Pages copy must be included in the site files and redeployed to become available to students.
