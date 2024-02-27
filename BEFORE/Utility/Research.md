---
database-plugin: basic
created: 2022-11-12 0923
updated: 2023-11-09 1406
---

```yaml:dbfolder
name: Research
description: My inputs into my Zettelkasten
columns:
  __file__:
    key: __file__
    id: __file__
    input: markdown
    label: File
    accessorKey: __file__
    isMetadata: true
    skipPersist: false
    isDragDisabled: false
    csvCandidate: true
    position: 1
    isHidden: false
    sortIndex: 0
    width: 30
    isSorted: true
    isSortedDesc: false
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: true
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      persist_formula: false
  __created__:
    key: __created__
    id: __created__
    input: metadata_time
    label: Created
    accessorKey: __created__
    isMetadata: true
    isDragDisabled: false
    skipPersist: false
    csvCandidate: true
    position: 2
    isHidden: false
    sortIndex: -1
    width: 172
    isSorted: false
    isSortedDesc: true
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      persist_formula: false
  __modified__:
    key: __modified__
    id: __modified__
    input: metadata_time
    label: Modified
    accessorKey: __modified__
    isMetadata: true
    isDragDisabled: false
    skipPersist: false
    csvCandidate: true
    position: 3
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      persist_formula: false
  __tasks__:
    key: __tasks__
    id: __tasks__
    input: task
    label: Task
    accessorKey: __tasks__
    isMetadata: true
    isDragDisabled: false
    skipPersist: false
    csvCandidate: false
    position: 4
    isHidden: true
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      persist_formula: false
  tags:
    input: tags
    accessorKey: tags
    key: tags
    id: tags
    label: tags
    position: 5
    skipPersist: false
    isHidden: false
    sortIndex: -1
    isSorted: false
    isSortedDesc: false
    width: 180
    options:
      - { label: "🧠️/📝️/🌱️", value: "🧠️/📝️/🌱️", color: "hsl(54, 95%, 90%)"}
      - { label: "🧠️/📥️/🎥️/🟥️", value: "🧠️/📥️/🎥️/🟥️", color: "hsl(85, 95%, 90%)"}
      - { label: "🧠️/📥️/🎥️/🟧️", value: "🧠️/📥️/🎥️/🟧️", color: "hsl(23, 95%, 90%)"}
      - { label: "🧠️/📝️/🌿️", value: "🧠️/📝️/🌿️", color: "hsl(321, 95%, 90%)"}
      - { label: "🧠️/📝️/🌲️", value: "🧠️/📝️/🌲️", color: "hsl(334, 95%, 90%)"}
      - { label: "🧠️/⚙️", value: "🧠️/⚙️", color: "hsl(40, 95%, 90%)"}
      - { label: "🧠️/📥️/📚️/🟩️", value: "🧠️/📥️/📚️/🟩️", color: "hsl(250, 95%, 90%)"}
      - { label: "🧠️/📥️/📜️/🟪️", value: "🧠️/📥️/📜️/🟪️", color: "hsl(352, 95%, 90%)"}
      - { label: "🧠️/📥️/🎥️/🟩️", value: "🧠️/📥️/🎥️/🟩️", color: "hsl(46, 95%, 90%)"}
      - { label: "🧠️/📥️/🎧️/🟩️", value: "🧠️/📥️/🎧️/🟩️", color: "hsl(351, 95%, 90%)"}
      - { label: "🧠️/📥️/📜️/🟧️", value: "🧠️/📥️/📜️/🟧️", color: "hsl(122, 95%, 90%)"}
      - { label: "🧠️/📥️/💭️/🟥️", value: "🧠️/📥️/💭️/🟥️", color: "hsl(95, 95%, 90%)"}
      - { label: "🧠️/📥️/🐦️/🟥️", value: "🧠️/📥️/🐦️/🟥️", color: "hsl(5, 95%, 90%)"}
      - { label: "🧠️/📥️/📰️/🟧️", value: "🧠️/📥️/📰️/🟧️", color: "hsl(114, 95%, 90%)"}
      - { label: "🧠️/📥️/📚️/🟧️", value: "🧠️/📥️/📚️/🟧️", color: "hsl(321, 95%, 90%)"}
      - { label: "🧠️/📥️/📚️/🟥️", value: "🧠️/📥️/📚️/🟥️", color: "hsl(16, 95%, 90%)"}
      - { label: "🧠️/📥️/📰️/🟥️", value: "🧠️/📥️/📰️/🟥️", color: "hsl(215, 95%, 90%)"}
      - { label: "🧠️/👥️", value: "🧠️/👥️", color: "hsl(209, 95%, 90%)"}
      - { label: "🧠️/🗺️", value: "🧠️/🗺️", color: "hsl(194, 95%, 90%)"}
      - { label: "🧠️/📝️/🌞️", value: "🧠️/📝️/🌞️", color: "hsl(314, 95%, 90%)"}
      - { label: "🧠️/✅️/🟥️", value: "🧠️/✅️/🟥️", color: "hsl(345, 95%, 90%)"}
      - { label: "🧠️/📥️/🐦️/🟩️", value: "🧠️/📥️/🐦️/🟩️", color: "hsl(226, 95%, 90%)"}
      - { label: "🧠️/📥️/📜️/🟩️", value: "🧠️/📥️/📜️/🟩️", color: "hsl(90, 95%, 90%)"}
      - { label: "🧠️/📥️/📰️/🟩️", value: "🧠️/📥️/📰️/🟩️", color: "hsl(51, 95%, 90%)"}
      - { label: "🧠️/📥️/💭️/🟩️", value: "🧠️/📥️/💭️/🟩️", color: "hsl(100, 95%, 90%)"}
      - { label: "🧠️/📥️/📚️/🟪️", value: "🧠️/📥️/📚️/🟪️", color: "hsl(281, 95%, 90%)"}
      - { label: "🧠️/📥️/📚️/", value: "🧠️/📥️/📚️/", color: "hsl(340, 95%, 90%)"}
      - { label: "gs", value: "gs", color: "hsl(208, 95%, 90%)"}
      - { label: "🧠️/📥️/📜️/🟥️", value: "🧠️/📥️/📜️/🟥️", color: "hsl(15, 95%, 90%)"}
      - { label: "🧠️/📥️/🔖️/🟩️", value: "🧠️/📥️/🔖️/🟩️", color: "hsl(271, 95%, 90%)"}
      - { label: "🧠️/📥️/🎧️/🟨️", value: "🧠️/📥️/🎧️/🟨️", color: "hsl(111, 95%, 90%)"}
      - { label: "📥️/🐦️/🟩️", value: "📥️/🐦️/🟩️", color: "hsl(261, 95%, 90%)"}
      - { label: "📥️/🐦️/🟥️", value: "📥️/🐦️/🟥️", color: "hsl(139, 95%, 90%)"}
      - { label: "📥️/🎧️/🟩️", value: "📥️/🎧️/🟩️", color: "hsl(158, 95%, 90%)"}
      - { label: "📥️/🎧️/🟨️", value: "📥️/🎧️/🟨️", color: "hsl(40, 95%, 90%)"}
      - { label: "📥️/📜️/🟩️", value: "📥️/📜️/🟩️", color: "hsl(277, 95%, 90%)"}
      - { label: "📥️/📜️/🟪️", value: "📥️/📜️/🟪️", color: "hsl(168, 95%, 90%)"}
      - { label: "📥️/📜️/🟧️", value: "📥️/📜️/🟧️", color: "hsl(319, 95%, 90%)"}
      - { label: "📥️/📰️/🟩️", value: "📥️/📰️/🟩️", color: "hsl(73, 95%, 90%)"}
      - { label: "📥️/📰️/🟧️", value: "📥️/📰️/🟧️", color: "hsl(339, 95%, 90%)"}
      - { label: "📥️/📰️/🟥️", value: "📥️/📰️/🟥️", color: "hsl(197, 95%, 90%)"}
      - { label: "📥️/🎥️/🟩️", value: "📥️/🎥️/🟩️", color: "hsl(300, 95%, 90%)"}
      - { label: "📥️/🎥️/🟧️", value: "📥️/🎥️/🟧️", color: "hsl(107, 95%, 90%)"}
      - { label: "📥️/🎥️/🟥️", value: "📥️/🎥️/🟥️", color: "hsl(56, 95%, 90%)"}
      - { label: "📥️/💭️/🟩️", value: "📥️/💭️/🟩️", color: "hsl(221, 95%, 90%)"}
      - { label: "📥️/💭️/🟥️", value: "📥️/💭️/🟥️", color: "hsl(24, 95%, 90%)"}
      - { label: "📥️/📚️/🟩️", value: "📥️/📚️/🟩️", color: "hsl(237, 95%, 90%)"}
      - { label: "📥️/🔖️/🟩️", value: "📥️/🔖️/🟩️", color: "hsl(153, 95%, 90%)"}
      - { label: "📥️/📚️/🟥️", value: "📥️/📚️/🟥️", color: "hsl(174, 95%, 90%)"}
      - { label: "📥️/📚️/🟧️", value: "📥️/📚️/🟧️", color: "hsl(312, 95%, 90%)"}
      - { label: "-", value: "-", color: "hsl(94, 95%, 90%)"}
      - { label: "reading, how to read", value: "reading, how to read", color: "hsl(74, 95%, 90%)"}
      - { label: "💻️/📥️/📚️/🟩️", value: "💻️/📥️/📚️/🟩️", color: "hsl(27, 95%, 90%)"}
      - { label: "📥️/🎧️/🟥️", value: "📥️/🎧️/🟥️", color: "hsl(193, 95%, 90%)"}
      - { label: "📥️/📰/🟥️", value: "📥️/📰/🟥️", color: "hsl(234, 95%, 90%)"}
      - { label: "📥️/📰/🟩️", value: "📥️/📰/🟩️", color: "hsl(330, 95%, 90%)"}
      - { label: "📥️/📰/🟧️", value: "📥️/📰/🟧️", color: "hsl(84, 95%, 90%)"}
      - { label: "📝️/🌲️", value: "📝️/🌲️", color: "hsl(30, 95%, 90%)"}
      - { label: "📝️/👥️", value: "📝️/👥️", color: "hsl(24, 95%, 90%)"}
      - { label: "📝️/🗺️", value: "📝️/🗺️", color: "hsl(50, 95%, 90%)"}
      - { label: "📝️/🌱️", value: "📝️/🌱️", color: "hsl(246, 95%, 90%)"}
      - { label: "📝️/🌿️", value: "📝️/🌿️", color: "hsl(190, 95%, 90%)"}
      - { label: "✅️/🟥️", value: "✅️/🟥️", color: "hsl(93, 95%, 90%)"}
      - { label: "📝️/🛥️", value: "📝️/🛥️", color: "hsl(109, 95%, 90%)"}
      - { label: "[[favorite|favorite]]", value: "[[favorite|favorite]]", color: "hsl(121, 95%, 90%)"}
      - { label: "📥️/🔖️/🟥️", value: "📥️/🔖️/🟥️", color: "hsl(207, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: true
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      persist_formula: false
config:
  remove_field_when_delete_column: false
  cell_size: compact
  sticky_first_column: false
  group_folder_column: 
  remove_empty_folders: false
  automatically_group_files: false
  hoist_files_with_empty_attributes: true
  show_metadata_created: true
  show_metadata_modified: true
  show_metadata_tasks: true
  show_metadata_inlinks: false
  show_metadata_outlinks: false
  source_data: query
  source_form_result: "FROM #📥️ AND !\"Readwise\""
  source_destination_path: Inbox
  frontmatter_quote_wrap: false
  row_templates_folder: /
  current_row_template: Templates/Inputs/Video.md
  pagination_size: 200
  enable_js_formulas: false
  formula_folder_path: /
  inline_default: true
  inline_new_position: top
  date_format: yyyy-MM-dd
  datetime_format: "yyyy-MM-dd HH:mm:ss"
  font_size: 16
  metadata_date_format: "yyyy-MM-dd HH:mm:ss"
  enable_footer: false
  implementation: default
  show_metadata_tags: false
filters:
  enabled: true
  conditions:
      - condition: AND
        disabled: true
        label: "🟥️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🟥️"
          type: text
      - condition: AND
        disabled: true
        label: "🟧️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🟧️"
          type: text
      - condition: AND
        disabled: true
        label: "🟨️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🟨️"
          type: text
      - condition: AND
        disabled: true
        label: "🟩️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🟩️"
          type: text
      - condition: AND
        disabled: true
        label: "🟪️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🟪️"
          type: text
      - field: tags
        operator: CONTAINS
        value: "📥️"
        type: text
      - field: tags
        operator: IS_NOT_EMPTY
        value: ""
        type: text
      - condition: AND
        disabled: true
        label: "🎥️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🎥️"
          type: text
      - condition: AND
        disabled: true
        label: "📰️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "📰"
          type: text
      - condition: AND
        disabled: true
        label: "📜️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "📜️"
          type: text
      - condition: AND
        disabled: true
        label: "🎧️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🎧️"
          type: text
      - condition: AND
        disabled: true
        label: "📚️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "📚️"
          type: text
      - condition: AND
        disabled: true
        label: "🐦️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🐦️"
          type: text
      - condition: AND
        disabled: true
        label: "💭️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "💭️"
          type: text
      - condition: AND
        disabled: true
        label: "🔖️"
        filters:
        - field: tags
          operator: CONTAINS
          value: "🔖️"
          type: text
```