# Continuum 0.47.1

A small Mac fix release: hover-highlighted menus are clickable again, and the empty-state composer's chip row sits centered under the box.

## Fixes

- **Hover-highlighted menus are clickable again.** A decorative hover wash had started sitting on top of the menu it was highlighting and swallowing the click, leaving the Settings provider pickers, the sidebar "Add project" menu, and the composer repo picker dead once you hovered them. The wash no longer intercepts the click. (#596)
- **A centered empty-state composer chip row.** The repo / account / location chips beneath the empty-state composer now center under the box instead of being pinned flush-left and poking out past the box's edge. (#595)
