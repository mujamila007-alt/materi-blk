# Mujahiid BLK Standalone

Project ini memisahkan Portal BLK dari website Mujahiid utama.

## Struktur

- `/blk/` — portal peserta BLK
- `/admin-blk/` — dashboard admin BLK
- `/api/supabase-storage.js` — API upload/delete Supabase Storage
- `/blk/*.zip` — file materi pelatihan
- `/blk/Profil_Usaha_Mujahidin.docx` — template profil usaha
- `firestore-rules-blk.rules` — rules Firestore BLK
- `storage-rules-blk.rules` — rules Firebase Storage BLK
- `SUPABASE-SETUP.sql` — setup Supabase
- `SUPABASE-RLS-CLEANUP-OPSIONAL.sql` — cleanup RLS opsional

## Hosting Vercel

Upload seluruh isi folder ini ke repository GitHub baru, lalu import repository tersebut ke Vercel.

Environment Variables yang diperlukan untuk API:

- `SUPABASE_URL`
- `SUPABASE_SECRET_KEY` — secret/service key, hanya di Vercel
- `SUPABASE_BUCKET` — default `blk-assets`
- `ADMIN_EMAILS` — email admin, dapat berupa beberapa email dipisahkan koma

Jangan memasukkan `SUPABASE_SECRET_KEY` ke file frontend.

## Firebase

Project ini masih menggunakan Firebase project yang sama dengan versi sebelumnya untuk Authentication dan Firestore. Setelah menggunakan domain baru, tambahkan domain Vercel/domain custom tersebut pada Firebase Authentication > Settings > Authorized domains.

## Supabase

Pastikan bucket `blk-assets` tersedia dan policy/RLS sesuai dengan SQL yang disediakan.
