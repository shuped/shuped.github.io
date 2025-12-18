# Tasks: Blog Foundation

**Input**: Design documents from `/specs/001-blog-foundation/`
**Prerequisites**: plan.md (required), spec.md (required)

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to

---

## Phase 1: Setup

**Purpose**: Project initialization and Jekyll configuration

- [ ] T001 Create Gemfile with Jekyll and GitHub Pages dependencies
- [ ] T002 Create _config.yml with site settings and author info
- [ ] T003 [P] Create .gitignore for Jekyll project

---

## Phase 2: Core Templates

**Purpose**: Base layouts and includes that all pages depend on

- [ ] T004 Create _includes/head.html with meta tags and CSS link
- [ ] T005 [P] Create _includes/header.html with site title and navigation
- [ ] T006 [P] Create _includes/footer.html with copyright and links
- [ ] T007 Create _layouts/default.html base template
- [ ] T008 Create _layouts/home.html for homepage
- [ ] T009 Create _layouts/post.html for blog posts

**Checkpoint**: Base templates ready for styling

---

## Phase 3: Styling

**Purpose**: CSS for professional appearance

- [ ] T010 Create _sass/_base.scss with typography and reset
- [ ] T011 [P] Create _sass/_layout.scss with page structure
- [ ] T012 [P] Create _sass/_syntax.scss for code highlighting
- [ ] T013 Create assets/css/main.scss to import all styles

**Checkpoint**: Visual design complete

---

## Phase 4: User Story 1 - Homepage (Priority: P1)

**Goal**: Professional homepage with author info and post list

**Independent Test**: Load homepage URL and verify content displays

- [ ] T014 [US1] Create index.html with post listing and author section
- [ ] T015 [US1] Add author bio section with professional info

**Checkpoint**: Homepage functional and styled

---

## Phase 5: User Story 2 - Blog Posts (Priority: P2)

**Goal**: Readable blog posts with proper formatting

**Independent Test**: Create sample post and verify it renders correctly

- [ ] T016 [US2] Create _posts/ directory structure
- [ ] T017 [US2] Create sample welcome post with code example
- [ ] T018 [US2] Verify code syntax highlighting works

**Checkpoint**: Posts render correctly with code highlighting

---

## Phase 6: User Story 3 - Categories (Priority: P3)

**Goal**: Browse posts by category

**Independent Test**: Navigate to category page and verify filtering

- [ ] T019 [US3] Create categories.html page listing all categories
- [ ] T020 [US3] Add category display to post layout
- [ ] T021 [US3] Add category links to homepage post list

**Checkpoint**: Category browsing functional

---

## Phase 7: Additional Pages

**Purpose**: Supporting pages

- [ ] T022 [P] Create about.md with author information
- [ ] T023 [P] Create 404.html custom error page

---

## Phase 8: Deployment

**Purpose**: GitHub Actions for automated deployment

- [ ] T024 Create .github/workflows/deploy.yml for GitHub Pages
- [ ] T025 Verify build succeeds locally
- [ ] T026 Push to GitHub and verify Actions run

**Checkpoint**: Blog deployed and accessible

---

## Phase 9: Validation

**Purpose**: Final checks

- [ ] T027 Verify homepage displays correctly
- [ ] T028 Verify sample post renders with syntax highlighting
- [ ] T029 Verify navigation works between pages
- [ ] T030 Verify mobile responsiveness
- [ ] T031 Ready for first real blog post

---

## Dependencies & Execution Order

### Phase Dependencies

- **Phase 1 (Setup)**: No dependencies
- **Phase 2 (Templates)**: Depends on Phase 1
- **Phase 3 (Styling)**: Depends on Phase 2
- **Phase 4-6 (User Stories)**: Depend on Phase 3
- **Phase 7 (Pages)**: Can run parallel to Phase 4-6
- **Phase 8 (Deployment)**: Depends on all content being ready
- **Phase 9 (Validation)**: Depends on Phase 8

### Parallel Opportunities

- T003, T004, T005, T006 can run in parallel after T001/T002
- T010, T011, T012 can run in parallel
- T022, T023 can run in parallel with user story phases
