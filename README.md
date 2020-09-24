# Projeto Integrador FATEC 20202, 1º Semestre ADS Grupo 3 📚
---


   
# We must fetch at least the immediate parents so that if this is
# a pull request then we can checkout the head.
fetch-depth: 2

# If this run was triggered by a pull request event, then checkout
# the head of the pull request instead of the merge commit.
- run: git checkout HEAD^2
if: ${{ github.event_name == 'pull_request' }}

# Initializes the CodeQL tools for scanning.
- name: Initialize CodeQL
uses: github/codeql-action/init@v1
# Override language selection by uncommenting this and choosing your languages
with:
languages: javascript

# Autobuild attempts to build any compiled languages  (C/C++, C#, or Java).
# If this step fails, then you should remove it and run the build manually (see below)
- name: Autobuild
uses: github/codeql-action/autobuild@v1

# ℹ️ Command-line programs to run using the OS shell.
#  https://git.io/JvXDl

# ✏️ If the Autobuild fails above, remove it and uncomment the following three lines
#    and modify them (or add more) to build your code if your project
#    uses a compiled language


